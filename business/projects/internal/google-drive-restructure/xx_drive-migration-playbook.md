---
title: "Drive Restructure & Migration — Playbook"
date: 2026-10-09
tags: [project, setup, tool, ai, strategy]
ai: claude
status: ok
---

# Drive Restructure & Migration — Playbook

## Summary
How to restructure a firm's Google Drive into the client-first AI-ready taxonomy and move all existing content in, using Claude for design and the skeleton and a person-run Apps Script for the moves. Proven on Blue Tusk's own drive on 2026-10-09 (726 items, 0 errors, about half a working day end to end). **Read this before doing it for a client (MOG first).** Living doc: update it after each run.

## Context
- Design: [[business/projects/internal/product/20261008_ai-native-operating-architecture]] Section 6 (Drive pattern) and 5.5 (contracts).
- Blue Tusk run log, with every decision and ID: [[20261009_blue-tusk-drive-skeleton-build]].
- The script: [[xx_drive-migration-script]] (full source). Move it into the skills repo when that exists.
- Connector test history: [[business/projects/internal/product/20261007_google-drive-taxonomy-test-results]].

---

## Content

### 1. What the AI connectors can and can't do in Drive (tested)

| Action | AI connector | Notes |
|---|---|---|
| Create folders | ✅ | One call per folder; parallel calls work. ~140 folders took a few minutes. |
| Rename files and folders | ✅ | Keeps ID and links. |
| Trash files and folders | ✅ | Trashing a folder trashes its contents. Restorable ~30 days. |
| **Move files or folders** | ❌ | Permission error even with Manager access. **This is the reason for the script.** |
| Create a Google Sheet with data | ✅ | Upload CSV with `contentMimeType: text/csv` → converts to a Sheet in one call. The tab comes out named "Untitled"; rename it with a batch update (look up the real `sheetId` first; it isn't 0). |
| Create a formatted Google Doc | ✅ | Upload markdown with `text/markdown` → converts to a Doc. **Markdown tables import with an empty header row:** use lists instead. Bold markers aren't in the doc text, so find-and-replace must match the plain text. |
| Edit a Doc | ✅ cheap | `replaceAllText` on plain text. If a structural rewrite is needed, recreating the Doc from markdown and trashing the old one is cheaper than positional edits. |
| Read a large Sheet | ⚠️ | A 700-row inventory exceeds the tool's output limit; it's saved to a file. Process it in code (Node/Python), never page through it in chat. |
| Search across the drive | ⚠️ | Returns other drives too and pages unpredictably. **Same-name folders exist across drives** (four "GhostOps" folders): always confirm the parent ID before trashing. |
| Items in trash | ⚠️ | Apps Script `getFiles()`/`getFolders()` can return trashed items. The script uses `searchFiles('trashed = false')`. |

### 2. The process (in order)

**A. Design (Claude + person, ~1 hour)**
1. Map the current drive (folders only) via the connector. Expect gaps; the inventory in step C is the real map.
2. Agree the client codes (3 letters, never reused) and project IDs `{CLIENT}-{YYMMDDNN}`. Projects without a known date: use the first of the month the person gives.
3. Agree the top-level structure. **Push back on folders that hold working documents** (strategy, offer definitions, playbooks): those belong in Notion. Drive holds finals, files, templates and records.
4. Decide where internal projects go (`01_Clients/{FIRM}_{slug}/`) and where lost proposals go (`99_Archive/02_Pipeline/Lost-Proposals`; never-won clients under `99_Archive/01_Clients/`).

**B. Skeleton (Claude, ~30 minutes)**
1. Check the root for clashes before creating anything.
2. Build the new tree **beside** the old one in the same shared drive. Moves within one drive keep IDs, links and sharing.
3. Every external client gets `00_Contracts/`; every project gets `client-sent/`, `in-progress/`, `delivered/`. Create the `99_Archive` mirror folders and year folders (e.g. `Receipts/2026`) the moves will need.
4. Write INDEX (Sheet, from CSV) and CONVENTIONS (Doc, from markdown) at the root.
5. Log every folder ID in INDEX. Log decisions in a run note in the vault.

**C. Migration (person runs, Claude writes rules)**
1. Create a migration sheet in the firm's internal restructure project folder (e.g. `BTK-26100701_drive-restructure/`). Claude seeds it: a **Rules** tab (CSV upload) and a **Config** tab (`SOURCE_ROOT_ID` = shared drive root; `EXCLUDE_NAMES` = INDEX, CONVENTIONS, any test folders; `EXCLUDE_PATTERN` = `^\d\d_` to skip the new structure).
2. Person: Extensions → Apps Script → paste the script → save → reload → **Migration → 0 (set up tabs)** → **1 (build inventory)**. Google asks for authorization the first time.
3. **Wait for the inventory to finish.** It resumes itself every minute after a ~4.5-minute run. Check the hidden `_Queue` tab: empty (header only) = done. Blue Tusk: ~10 minutes for 726 items. **Don't plan off a half-finished inventory:** the first read showed rules as "not found" because Legal hadn't been walked yet.
4. Claude reads the Inventory (saved to file), runs the script's own `computePlan_` locally in Node against it, and iterates the rules until there are **0 errors** and the **unmapped list** is only what's meant to stay. Report "files covered / total files" (Blue Tusk: 527/546).
5. Claude proposes destinations for every unmapped item; the person confirms the judgement calls. Add rules in batches (`append_values`).
6. Person: **2 (build plan, dry run)** → review → **3 (execute)** → **4 (list empty folders)** → **5 (trash them)**. Re-run 2 whenever rules change.
7. Claude checks the Log tab (every row `done`) and lists what's left at the root.

**D. Close-out**
1. Person moves anything secret (e.g. `XX_Logins`) to a password manager, then deletes it.
2. Convert remaining strategy/offer docs to Notion pages; file sheets and images in Drive.
3. Update INDEX, CONVENTIONS, the architecture doc and the run note. Update this playbook with anything new.

### 3. Rule-writing patterns (Rules tab)
- **`move_contents` on old project folders → new project folder.** The old folder empties and is cleaned up in step 5.
- **`move_contents` on the old client folder → new client folder** catches loose client-level files. Deeper rules run first, so the project rule wins for the project subfolder.
- **`move` with `rename_to`** fixes typos and names in the same pass (`2024 Reciepts` → `2024`).
- **`skip`** protects anything that must not move (credentials folder). Skipped items still count as "not empty", so their parents survive step 5.
- **Individual file rules beat folder rules.** Use them to pull client material out of company folders (e.g. a client's T&C redline sitting in `Legal/Contracts/Examples` → that client's `00_Contracts`).
- **Paths must match the Inventory exactly.** File names containing `/` (e.g. `Rocky Fischer // Cause Crazy - SOW`) still work: the script matches the whole path string.
- Rules for unknown folders surface as ERROR rows in the dry run; nothing moves for them. Draft rules from the map early, fix them against the inventory.

### 4. Where things usually go (defaults to propose)

| Found in old drive | Goes to |
|---|---|
| Signed MSAs, SOWs, NDAs (often scattered in Legal, Sales/SOW/Sold) | Client's `00_Contracts` (one signed copy only) |
| Contracts signed on another platform | Same; the Drive copy of the final is the record |
| Blank MSA/SOW/NDA/proposal templates, ROI calculators | `04_Knowledge/Proposal-Templates` (NDA template: `00_Company/Legal`) |
| Delivery templates, offer kits | `04_Knowledge/Delivery-Templates` |
| Courses, reference PDFs, cost calculators | `04_Knowledge` |
| Lost or never-signed proposals | `99_Archive/02_Pipeline/Lost-Proposals`, or the archived client folder if one exists |
| Company legal (LLC, tax, HIPAA) | `00_Company/Legal` |
| Receipts, bookkeeping | `00_Company/Finance/Receipts/{YYYY}`, `Bookkeeping/{YYYY}` |
| Financial models, cash flow, loans | `00_Company/Finance/Planning` |
| Logos, headshots, style guide | `03_Marketing/Brand-Assets` |
| Blog, social, content plans | `03_Marketing/Content` |
| One-pagers, data sheets, whitepapers | `03_Marketing/Sales-Collateral` |
| Cold email, scripts, lead lists, outreach trackers | `02_Pipeline/Outreach` |
| Vendors, advisors, referral partners | `02_Pipeline/Partners` |
| Old 1–2-year-old working docs | `99_Archive/00_Company` |
| **Strategy, offer definitions, brainstorms, personas** | **Notion** (Knowledge), not Drive |
| Credentials | **Password manager**, never Drive |
| Shortcuts | Usually trash: one source of truth, linked from Notion |

### 5. Gotchas from the Blue Tusk run
- **The old map missed a whole folder of signed SOWs.** Always trust the inventory over the map.
- **"Duplicates" are often shortcuts** (`application/vnd.google-apps.shortcut`). Check the MIME type before calling something a duplicate.
- **Client material hides in company folders** (examples, templates). Scan company-level folders for client names.
- **Vault folder dates and Drive dates can disagree** (CauseCrazy vault 20251221 vs Drive 20251217). The person picks; record it in INDEX notes.
- **Running steps 2–3 twice is harmless:** moving an item to the folder it's already in does nothing (it just logs twice).
- **Empty-folder cleanup is safe** once execute is done: it only trashes folders with no files at any depth, honours exclusions, and everything is restorable from trash.
- **Restricting one folder inside a shared drive** (for `00_Contracts`) needs checking per firm; a separate small contracts drive is the fallback.

### 6. For a client engagement (MOG and after)
- Run it on **the client's** shared drive, with the client's admin running the script (they own the files). Claude never needs move permission.
- Budget: ~1 hour design call, ~30 minutes skeleton, inventory time scales with item count (assume ~1 minute per 70–100 items), one review call for unmapped items and judgement calls.
- The script and rule patterns are reusable as-is; only Config, Rules and destination IDs change.
- Log a client-specific run note like [[20261009_blue-tusk-drive-skeleton-build]] in the client's vault project folder.

## Next steps
- [ ] Move the script into the skills repo as part of a `drive-migration` skill.
- [ ] Check whether a single folder in a shared drive can be restricted (for `00_Contracts`) before MOG.
- [ ] After the MOG run, update sections 5 and 6 with what changed.
