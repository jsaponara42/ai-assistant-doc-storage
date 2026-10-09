---
title: "Drive Migration — Apps Script (v1)"
date: 2026-10-09
tags: [tool, setup, ai]
ai: claude
status: ok
---

# Drive Migration — Apps Script (v1)

## Summary
Full source of the rule-based Drive migration script, tested on Blue Tusk's shared drive on 2026-10-09 (726 items, 0 errors). Paste it into a Google Sheet's Apps Script editor. How to use it: [[xx_drive-migration-playbook]].

## Context
- Runs as the person who clicks the menu, so it can move files that AI connectors can't.
- `computePlan_` is pure: Claude can run it locally in Node against an exported Inventory to check rules before the person runs the dry run.
- Copy is also at `/home/claude/20261009_drive_migration.gs` in the 2026-10-09 session (ephemeral). This note is the source of truth until the skills repo exists.

## Content

```javascript
/**
 * Drive Migration: rule-based bulk mover for Google Drive (shared drives supported)
 * Blue Tusk LLC, v1, 2026-10-09
 *
 * Bound to a migration Google Sheet (Extensions > Apps Script). Runs as the person who
 * clicks the menu, so it can move files that AI connectors can't.
 *
 * WORKFLOW
 *   0. Migration > 0. Set up tabs        Creates Config / Rules / Inventory / Plan / Log tabs.
 *   1. Fill in Config (SOURCE_ROOT_ID, exclusions).
 *   2. Migration > 1. Build inventory    Lists every folder and file under the source, with paths.
 *   3. Fill in Rules (Claude writes these from the inventory).
 *   4. Migration > 2. Build plan         DRY RUN. Writes the Plan tab. Nothing moves.
 *   5. Review Plan: ERROR rows (bad rules), UNMAPPED rows (nothing will touch them), MOVE rows.
 *   6. Migration > 3. Execute plan       Moves every MOVE row, logs each result. Resumes itself
 *                                         if it runs past Apps Script's time limit.
 *   7. Migration > 4. List empty source folders, then 5. Trash them (optional).
 *
 * RULES TAB
 *   source_path  Path exactly as it appears in the Inventory tab, e.g. "Client Projects/LendForGood".
 *   action       move           Move the item itself (file or folder) into dest_id.
 *                move_contents  Move each direct child of the folder into dest_id; the folder stays (empty).
 *                skip           Leave it, and everything under it, where it is.
 *   dest_id      Destination folder ID (from INDEX). Not needed for skip.
 *   rename_to    Optional. New name for the item (move only).
 *   Deeper rules always win and run first, so a specific rule inside a broader one is safe.
 */

const TABS = {
  config: 'Config',
  rules: 'Rules',
  inventory: 'Inventory',
  plan: 'Plan',
  log: 'Log',
  queue: '_Queue',
};

const HEADERS = {
  config: ['key', 'value', 'notes'],
  rules: ['source_path', 'action', 'dest_id', 'rename_to', 'notes'],
  inventory: ['path', 'id', 'type', 'mime_type', 'parent_id', 'depth', 'modified', 'size_bytes'],
  plan: ['step', 'action', 'item_type', 'item_path', 'item_id', 'dest_id', 'dest_name', 'rename_to', 'rule', 'status'],
  log: ['timestamp', 'step', 'action', 'item_path', 'item_id', 'dest_id', 'result', 'detail'],
  queue: ['folder_id', 'path', 'depth'],
};

const CONFIG_DEFAULTS = [
  ['SOURCE_ROOT_ID', '', 'Folder or shared drive ID to migrate FROM'],
  ['EXCLUDE_NAMES', 'INDEX,CONVENTIONS,Taxonomy Test', 'Comma-separated top-level names to leave out of the inventory'],
  ['EXCLUDE_PATTERN', '^\\d\\d_', 'Regex: top-level names matching this are left out (the new structure)'],
];

const MAX_RUNTIME_MS = 4.5 * 60 * 1000; // Apps Script stops at 6 minutes
const PROP_JOB = 'MIGRATION_JOB';
const PROP_EXEC_ROW = 'MIGRATION_EXEC_ROW';

// ---------------------------------------------------------------------------
// Menu and setup
// ---------------------------------------------------------------------------

function onOpen() {
  SpreadsheetApp.getUi()
    .createMenu('Migration')
    .addItem('0. Set up tabs', 'setupTabs')
    .addSeparator()
    .addItem('1. Build inventory', 'startInventory')
    .addItem('2. Build plan (dry run)', 'buildPlan')
    .addItem('3. Execute plan', 'startExecute')
    .addSeparator()
    .addItem('4. List empty source folders', 'listEmptySourceFolders')
    .addItem('5. Trash empty source folders', 'trashEmptySourceFolders')
    .addSeparator()
    .addItem('Stop running job', 'stopJobs')
    .addToUi();
}

function setupTabs() {
  const ss = SpreadsheetApp.getActive();
  Object.keys(TABS).forEach(function (key) {
    let sh = ss.getSheetByName(TABS[key]);
    if (!sh) sh = ss.insertSheet(TABS[key]);
    if (sh.getLastRow() === 0) {
      sh.getRange(1, 1, 1, HEADERS[key].length).setValues([HEADERS[key]]).setFontWeight('bold');
      sh.setFrozenRows(1);
    }
    if (key === 'queue') sh.hideSheet();
  });
  const cfg = ss.getSheetByName(TABS.config);
  if (cfg.getLastRow() < 2) {
    cfg.getRange(2, 1, CONFIG_DEFAULTS.length, 3).setValues(CONFIG_DEFAULTS);
  }
  toast_('Tabs ready.');
}

// ---------------------------------------------------------------------------
// 1. Inventory (resumable depth-first walk; queue kept in a hidden tab)
// ---------------------------------------------------------------------------

function startInventory() {
  setupTabs();
  const cfg = getConfig_();
  if (!cfg.SOURCE_ROOT_ID) throw new Error('Set SOURCE_ROOT_ID on the Config tab first.');
  DriveApp.getFolderById(cfg.SOURCE_ROOT_ID); // fails early if the ID is wrong
  clearBody_(sheet_(TABS.inventory));
  const q = sheet_(TABS.queue);
  clearBody_(q);
  q.appendRow([cfg.SOURCE_ROOT_ID, '', 0]);
  setJob_('inventory');
  runInventory();
}

function runInventory() {
  const start = Date.now();
  const cfg = getConfig_();
  const excludeNames = cfg.EXCLUDE_NAMES.split(',').map(function (s) { return s.trim(); }).filter(String);
  const excludeRe = cfg.EXCLUDE_PATTERN ? new RegExp(cfg.EXCLUDE_PATTERN) : null;
  const q = sheet_(TABS.queue);
  const inv = sheet_(TABS.inventory);

  while (q.getLastRow() >= 2) {
    if (Date.now() - start > MAX_RUNTIME_MS) {
      scheduleResume_('runInventory');
      toast_('Inventory still running; it will resume in about a minute.');
      return;
    }
    const last = q.getLastRow();
    const entry = q.getRange(last, 1, 1, 3).getValues()[0];
    const folder = DriveApp.getFolderById(entry[0]);
    const basePath = entry[1];
    const depth = Number(entry[2]);
    const rows = [];
    const childQueue = [];

    const isExcluded = function (name) {
      if (depth !== 0) return false; // exclusions apply to top-level items only
      return excludeNames.indexOf(name) !== -1 || (excludeRe && excludeRe.test(name));
    };

    const subfolders = folder.searchFolders('trashed = false');
    while (subfolders.hasNext()) {
      const f = subfolders.next();
      const name = f.getName();
      if (isExcluded(name)) continue;
      const path = basePath ? basePath + '/' + name : name;
      rows.push([path, f.getId(), 'folder', 'application/vnd.google-apps.folder', folder.getId(), depth + 1, f.getLastUpdated(), '']);
      childQueue.push([f.getId(), path, depth + 1]);
    }
    const files = folder.searchFiles('trashed = false');
    while (files.hasNext()) {
      const file = files.next();
      const name = file.getName();
      if (isExcluded(name)) continue;
      const path = basePath ? basePath + '/' + name : name;
      rows.push([path, file.getId(), 'file', file.getMimeType(), folder.getId(), depth + 1, file.getLastUpdated(), file.getSize()]);
    }

    // Pop this folder, push its children, then write its rows (only after the folder is fully read).
    q.deleteRow(last);
    if (childQueue.length) q.getRange(q.getLastRow() + 1, 1, childQueue.length, 3).setValues(childQueue);
    if (rows.length) inv.getRange(inv.getLastRow() + 1, 1, rows.length, HEADERS.inventory.length).setValues(rows);
  }

  finishJob_();
  sortInventory_();
  toast_('Inventory done: ' + (inv.getLastRow() - 1) + ' items.');
}

function sortInventory_() {
  const inv = sheet_(TABS.inventory);
  if (inv.getLastRow() > 2) inv.getRange(2, 1, inv.getLastRow() - 1, HEADERS.inventory.length).sort(1);
}

// ---------------------------------------------------------------------------
// 2. Plan (dry run). computePlan_ is pure so it can be tested outside Apps Script.
// ---------------------------------------------------------------------------

function buildPlan() {
  const inventory = readTable_(TABS.inventory);
  const rules = readTable_(TABS.rules);
  if (!inventory.length) throw new Error('Inventory is empty. Run 1. Build inventory first.');

  const result = computePlan_(inventory, rules);

  // Validate destinations and fetch their names (the only Drive calls in the dry run).
  const destNames = {};
  result.moves.forEach(function (m) {
    if (destNames[m.dest_id] !== undefined) return;
    try { destNames[m.dest_id] = DriveApp.getFolderById(m.dest_id).getName(); }
    catch (e) { destNames[m.dest_id] = null; }
  });

  const out = [];
  let step = 0;
  result.errors.forEach(function (e) {
    out.push(['', 'ERROR', '', e.source_path, '', e.dest_id || '', '', '', e.source_path, e.message]);
  });
  result.moves.forEach(function (m) {
    step++;
    const destName = destNames[m.dest_id];
    const status = destName === null ? 'ERROR: destination not found' : 'planned';
    out.push([step, 'MOVE', m.type, m.path, m.id, m.dest_id, destName || '', m.rename_to || '', m.rule, status]);
  });
  result.unmapped.forEach(function (u) {
    out.push(['', 'UNMAPPED', u.type, u.path, u.id, '', '', '', '', 'no rule; stays in place']);
  });

  const plan = sheet_(TABS.plan);
  clearBody_(plan);
  if (out.length) plan.getRange(2, 1, out.length, HEADERS.plan.length).setValues(out);
  PropertiesService.getScriptProperties().deleteProperty(PROP_EXEC_ROW);
  toast_('Plan: ' + result.moves.length + ' moves, ' + result.errors.length + ' errors, ' + result.unmapped.length + ' unmapped. Nothing has moved.');
}

/**
 * @param {Object[]} inventory rows {path, id, type, parent_id, depth}
 * @param {Object[]} rules rows {source_path, action, dest_id, rename_to}
 * @return {{moves: Object[], errors: Object[], unmapped: Object[]}}
 */
function computePlan_(inventory, rules) {
  const byPath = {};
  const byId = {};
  const children = {};
  inventory.forEach(function (it) {
    it.depth = Number(it.depth);
    byPath[String(it.path)] = it;
    byId[it.id] = it;
    (children[it.parent_id] = children[it.parent_id] || []).push(it);
  });

  const errors = [];
  const resolved = [];
  const seen = {};
  rules.forEach(function (r) {
    const sp = String(r.source_path || '').trim();
    const action = String(r.action || '').trim().toLowerCase();
    if (!sp && !action) return; // blank row
    const dest = String(r.dest_id || '').trim();
    const item = byPath[sp];
    if (['move', 'move_contents', 'skip'].indexOf(action) === -1) {
      errors.push({ source_path: sp, dest_id: dest, message: 'Unknown action "' + action + '"' });
    } else if (!item) {
      errors.push({ source_path: sp, dest_id: dest, message: 'source_path not found in Inventory' });
    } else if (action !== 'skip' && !dest) {
      errors.push({ source_path: sp, dest_id: dest, message: 'dest_id missing' });
    } else if (action === 'move_contents' && item.type !== 'folder') {
      errors.push({ source_path: sp, dest_id: dest, message: 'move_contents needs a folder' });
    } else if (seen[sp]) {
      errors.push({ source_path: sp, dest_id: dest, message: 'Duplicate rule for this path' });
    } else {
      seen[sp] = true;
      resolved.push({ item: item, action: action, dest: dest, rename: String(r.rename_to || '').trim(), sp: sp });
    }
  });

  // Deepest first: specific rules run before broader ones, so nested moves happen before parents move.
  resolved.sort(function (a, b) { return b.item.depth - a.item.depth; });

  const claimed = {}; // ids whose whole subtree is handled
  const moves = [];
  resolved.forEach(function (r) {
    if (isCovered_(r.item.id, claimed, byId)) return; // inside something already handled
    if (r.action === 'skip') {
      claimed[r.item.id] = true;
    } else if (r.action === 'move') {
      moves.push({ id: r.item.id, path: r.item.path, type: r.item.type, dest_id: r.dest, rename_to: r.rename, rule: r.sp + ' [move]' });
      claimed[r.item.id] = true;
    } else { // move_contents
      (children[r.item.id] || []).forEach(function (c) {
        if (claimed[c.id]) return;
        moves.push({ id: c.id, path: c.path, type: c.type, dest_id: r.dest, rename_to: '', rule: r.sp + ' [move_contents]' });
        claimed[c.id] = true;
      });
      claimed[r.item.id] = true; // the emptied folder stays; parents must not sweep it up
    }
  });

  // Ancestors of anything handled are "containers": partly mapped, so report their leftovers individually.
  const containers = {};
  Object.keys(claimed).forEach(function (id) {
    let p = byId[id] ? byId[id].parent_id : null;
    while (p && byId[p]) { containers[p] = true; p = byId[p].parent_id; }
  });

  // Report the top-most items that nothing will touch.
  const unmapped = [];
  inventory.forEach(function (it) {
    if (isCovered_(it.id, claimed, byId) || containers[it.id]) return;
    const parent = byId[it.parent_id];
    if (!parent || containers[parent.id]) unmapped.push({ id: it.id, path: it.path, type: it.type });
  });
  unmapped.sort(function (a, b) { return String(a.path) < String(b.path) ? -1 : 1; });

  return { moves: moves, errors: errors, unmapped: unmapped };
}

function isCovered_(id, claimed, byId) {
  let cur = id;
  while (cur) {
    if (claimed[cur]) return true;
    cur = byId[cur] ? byId[cur].parent_id : null;
  }
  return false;
}

// ---------------------------------------------------------------------------
// 3. Execute (resumable; re-running skips rows already marked done)
// ---------------------------------------------------------------------------

function startExecute() {
  const ui = SpreadsheetApp.getUi();
  const plan = readTable_(TABS.plan);
  const pending = plan.filter(function (r) { return r.action === 'MOVE' && r.status === 'planned'; }).length;
  const errors = plan.filter(function (r) { return String(r.status).indexOf('ERROR') === 0 || r.action === 'ERROR'; }).length;
  if (!pending) { ui.alert('No planned moves. Run 2. Build plan first.'); return; }
  const msg = 'Move ' + pending + ' items now?' + (errors ? '\n\n' + errors + ' ERROR rows will be skipped. Fix them first if they matter.' : '');
  if (ui.alert('Execute plan', msg, ui.ButtonSet.OK_CANCEL) !== ui.Button.OK) return;
  PropertiesService.getScriptProperties().setProperty(PROP_EXEC_ROW, '2');
  setJob_('execute');
  runExecute();
}

function runExecute() {
  const start = Date.now();
  const props = PropertiesService.getScriptProperties();
  const plan = sheet_(TABS.plan);
  const log = sheet_(TABS.log);
  const lastRow = plan.getLastRow();
  let row = Number(props.getProperty(PROP_EXEC_ROW) || 2);
  const destCache = {};
  let done = 0;
  let failed = 0;

  for (; row <= lastRow; row++) {
    if (Date.now() - start > MAX_RUNTIME_MS) {
      props.setProperty(PROP_EXEC_ROW, String(row));
      scheduleResume_('runExecute');
      toast_('Still moving; it will resume in about a minute (row ' + row + ').');
      return;
    }
    const r = plan.getRange(row, 1, 1, HEADERS.plan.length).getValues()[0];
    const step = r[0], action = r[1], type = r[2], path = r[3], id = r[4], destId = r[5], rename = r[7], status = r[9];
    if (action !== 'MOVE' || status !== 'planned') continue;

    let result = 'done';
    let detail = '';
    try {
      const dest = destCache[destId] || (destCache[destId] = DriveApp.getFolderById(destId));
      const item = type === 'folder' ? DriveApp.getFolderById(id) : DriveApp.getFileById(id);
      item.moveTo(dest);
      if (rename) item.setName(rename);
      done++;
    } catch (e) {
      result = 'error';
      detail = e.message;
      failed++;
    }
    plan.getRange(row, 10).setValue(result === 'done' ? 'done' : 'error: ' + detail);
    log.appendRow([new Date(), step, action, path, id, destId, result, detail]);
  }

  props.deleteProperty(PROP_EXEC_ROW);
  finishJob_();
  toast_('Execute finished. Moved ' + done + (failed ? ', ' + failed + ' errors (see Log).' : '.'));
}

// ---------------------------------------------------------------------------
// 4/5. Empty-folder cleanup (only folders with no files anywhere beneath them)
// ---------------------------------------------------------------------------

function listEmptySourceFolders() {
  const empties = findEmptyFolders_();
  const log = sheet_(TABS.log);
  empties.forEach(function (e) { log.appendRow([new Date(), '', 'EMPTY', e.path, e.id, '', 'listed', '']); });
  toast_(empties.length + ' empty folders listed on the Log tab.');
}

function trashEmptySourceFolders() {
  const ui = SpreadsheetApp.getUi();
  const empties = findEmptyFolders_();
  if (!empties.length) { ui.alert('No empty folders found.'); return; }
  if (ui.alert('Trash empty folders', 'Move ' + empties.length + ' empty folders to trash? They can be restored from Drive trash.', ui.ButtonSet.OK_CANCEL) !== ui.Button.OK) return;
  const log = sheet_(TABS.log);
  empties.forEach(function (e) {
    try { DriveApp.getFolderById(e.id).setTrashed(true); log.appendRow([new Date(), '', 'TRASH', e.path, e.id, '', 'trashed', '']); }
    catch (err) { log.appendRow([new Date(), '', 'TRASH', e.path, e.id, '', 'error', err.message]); }
  });
  toast_('Trashed ' + empties.length + ' empty folders.');
}

/** Top-most source folders with no files anywhere inside. Honours the Config exclusions. */
function findEmptyFolders_() {
  const cfg = getConfig_();
  const excludeNames = cfg.EXCLUDE_NAMES.split(',').map(function (s) { return s.trim(); }).filter(String);
  const excludeRe = cfg.EXCLUDE_PATTERN ? new RegExp(cfg.EXCLUDE_PATTERN) : null;
  const root = DriveApp.getFolderById(cfg.SOURCE_ROOT_ID);
  const empties = [];

  function walk(folder, path) { // returns true if the folder holds no files at any depth
    const found = [];
    let empty = !folder.searchFiles('trashed = false').hasNext();
    const subs = folder.searchFolders('trashed = false');
    while (subs.hasNext()) {
      const s = subs.next();
      const p = path ? path + '/' + s.getName() : s.getName();
      if (walk(s, p)) found.push({ id: s.getId(), path: p });
      else empty = false;
    }
    if (!empty) found.forEach(function (f) { empties.push(f); }); // keep only top-most empties
    return empty;
  }

  const top = root.searchFolders('trashed = false');
  while (top.hasNext()) {
    const f = top.next();
    const name = f.getName();
    if (excludeNames.indexOf(name) !== -1 || (excludeRe && excludeRe.test(name))) continue;
    if (walk(f, name)) empties.push({ id: f.getId(), path: name });
  }
  return empties;
}

// ---------------------------------------------------------------------------
// Helpers
// ---------------------------------------------------------------------------

function sheet_(name) {
  const sh = SpreadsheetApp.getActive().getSheetByName(name);
  if (!sh) throw new Error('Missing tab "' + name + '". Run 0. Set up tabs.');
  return sh;
}

function clearBody_(sh) {
  if (sh.getLastRow() > 1) sh.getRange(2, 1, sh.getLastRow() - 1, sh.getLastColumn()).clearContent();
}

function readTable_(name) {
  const sh = sheet_(name);
  if (sh.getLastRow() < 2) return [];
  const values = sh.getRange(1, 1, sh.getLastRow(), sh.getLastColumn()).getValues();
  const head = values.shift();
  return values.map(function (row) {
    const o = {};
    head.forEach(function (h, i) { o[h] = row[i]; });
    return o;
  });
}

function getConfig_() {
  const cfg = { SOURCE_ROOT_ID: '', EXCLUDE_NAMES: '', EXCLUDE_PATTERN: '' };
  readTable_(TABS.config).forEach(function (r) { if (r.key) cfg[r.key] = String(r.value).trim(); });
  return cfg;
}

function setJob_(name) { PropertiesService.getScriptProperties().setProperty(PROP_JOB, name); }

function finishJob_() {
  PropertiesService.getScriptProperties().deleteProperty(PROP_JOB);
  deleteTriggers_();
}

function scheduleResume_(fnName) {
  deleteTriggers_();
  ScriptApp.newTrigger(fnName).timeBased().after(60 * 1000).create();
}

function deleteTriggers_() {
  ScriptApp.getProjectTriggers().forEach(function (t) {
    if (['runInventory', 'runExecute'].indexOf(t.getHandlerFunction()) !== -1) ScriptApp.deleteTrigger(t);
  });
}

function stopJobs() {
  deleteTriggers_();
  const props = PropertiesService.getScriptProperties();
  props.deleteProperty(PROP_JOB);
  toast_('Stopped. Re-running a step picks up from where it left off (Execute skips rows already done).');
}

function toast_(msg) {
  try { SpreadsheetApp.getActive().toast(msg, 'Migration', 8); } catch (e) { /* no UI when run from a trigger */ }
}
```

## Local plan check (Node)
Claude runs this against the exported Inventory and Rules JSON before the person runs the dry run:

```javascript
// node plan.js script.js inventory.json rules.json
const fs = require('fs');
eval(fs.readFileSync(process.argv[2], 'utf8') + ';global.computePlan_=computePlan_;');
const toRows = v => { const h = v.shift(); return v.map(r => Object.fromEntries(h.map((k, i) => [k, r[i] || '']))); };
const inv = toRows(JSON.parse(fs.readFileSync(process.argv[3])).values);
const rules = toRows(JSON.parse(fs.readFileSync(process.argv[4])).values);
const res = computePlan_(inv, rules);
console.log('errors', res.errors, 'moves', res.moves.length, 'unmapped', res.unmapped.map(u => u.path));
```
