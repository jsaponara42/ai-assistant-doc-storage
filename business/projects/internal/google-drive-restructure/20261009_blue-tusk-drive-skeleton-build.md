---
title: "Blue Tusk Drive Skeleton — Build Log"
date: 2026-10-09
tags: [project, setup, tool, ai]
ai: claude
status: needs-attention
---

# Blue Tusk Drive Skeleton — Build Log

## Summary
On 2026-10-09 Claude built the new client-first skeleton in the existing Blue Tusk shared drive, plus **INDEX** (Google Sheet) and **CONVENTIONS** (Google Doc) at the root. No existing files were touched. Content moves run through a **rule-based Apps Script** (dry run first), which is also the test of bulk migration for MOG and future clients.

## Context
Item 1 on the out-of-scope list in [[business/projects/internal/product/20261008_notion-build-spec-sandbox]]. Structure follows architecture Section 6 ([[business/projects/internal/product/20261008_ai-native-operating-architecture]]) and the Drive map ([[20261007_blue-tusk-drive-map-and-proposed-taxonomy]]). Blue Tusk is the template for MOG.

## Content

### Decisions (JC, 2026-10-09)
- **Client codes confirmed:** MOG, LFG, RFG, MAY, CAP, NWC, CCZ, EHM, RWR, SYN, PRC, BTK. (MAY vs Martina's "MC" still to settle with her.)
- **Built in the existing Blue Tusk shared drive,** beside the old folders.
- **Internal projects live under `01_Clients/BTK_blue-tusk/`.**
- **INDEX is a Google Sheet;** CONVENTIONS is a Google Doc.
- **`04_Offers` dropped.** Offer definitions, playbooks and strategy are living internal docs and belong in Notion. The only offer material that's ever final in Drive is a client-facing info sheet, which is sales collateral → **`03_Marketing/Sales-Collateral/`**. Blank templates (proposal and delivery) moved to **`04_Knowledge/`** (renumbered from 05). *Architecture Section 6 still shows `04_Offers` and needs the same change.*
- **Project IDs set:** `CCZ-25121701`, `PRC-25060101`, `EHM-25050101`, `RWR-25070101`, `SYN-25020101` (proposal only, never a project; lives in `99_Archive/01_Clients/`), `BTK-26100701` (drive restructure).
- **Migration by script, not by hand.**

### Key IDs
- Shared drive root: `0ADcQ-34uTjUgUk9PVA`
- INDEX (Sheet): `1YVVuW421oLG-p_l8yv8Rxv_6ViLogVLLkJB7XgKBJq8`
- CONVENTIONS (Doc): `1T5MqxdmO9ml6-Ov0iXwnbIGMjNdHCAnbvTTsRBTftYk` (rebuilt; the first version is in trash)
- Migration sheet: `1eD-qhkPDpiHNpAF8iTymXrPugXblJYEUQKUE1XIFD4s` (in `01_Clients/BTK_blue-tusk/BTK-26100701_drive-restructure/`)
- **Every folder ID is in INDEX.** INDEX is the source of truth; this note doesn't duplicate it.

### Current structure
```
00_Company/   Admin · Legal · Finance (Bookkeeping · Receipts/2026 · Planning)
01_Clients/   MOG LFG RFG MAY CAP NWC CCZ EHM RWR PRC BTK (each external client has 00_Contracts;
              each project has client-sent · in-progress · delivered)
02_Pipeline/  Outreach · Partners
03_Marketing/ Brand-Assets · Content · Lead-Magnets · Sales-Collateral
04_Knowledge/ Proposal-Templates · Delivery-Templates
99_Archive/   00_Company · 01_Clients (SYN_syncscript/SYN-25020101_proposal) · 03_Marketing
```

### Migration script (`20261009_drive_migration.gs`)
- **Bound to the migration sheet** (Extensions → Apps Script). Runs as JC, so it can move files that AI connectors can't.
- **Steps:** set up tabs → build inventory (every folder and file under the source, with paths) → build plan (**dry run**) → execute → list and trash empty source folders.
- **Rules tab:** `source_path`, `action` (`move` / `move_contents` / `skip`), `dest_id`, `rename_to`. Deeper rules always win, so specific rules can sit inside broad ones.
- **Plan tab shows** MOVE rows, ERROR rows (bad paths, missing IDs, duplicates) and UNMAPPED rows (nothing touches them).
- **Resumable:** stops before Apps Script's 6-minute limit and restarts itself a minute later. Execute skips rows already done. Every move is logged.
- **Skips trashed items** and the new structure (Config exclusions).
- **Tested locally** on sample data: nested rules, skip, move_contents, renames, bad/duplicate rules, unmapped reporting all behave as intended. **Not yet run in Apps Script.**
- **Rules pre-filled** (58) from the Oct 7 map. `XX_Logins` is set to `skip`. Anything the map got wrong shows as an ERROR row.

### Decisions on the leftover folders (JC, 2026-10-09)
- **AGP** (agency course materials) and **Project Resources** → `04_Knowledge`. Rules added.
- **GhostOps** → deleted. Trashed by Claude 2026-10-09; it held only a shortcut. Restorable from trash for 30 days.
- **Signed NDAs are kept** and filed with the client they belong to: PineRun → `PRC_pine-run-construction/00_Contracts`, SyncScript → `99_Archive/01_Clients/SYN_syncscript`. The blank `Blue Tusk Mutual NDA.docx` → `00_Company/Legal`. Rules added.
- **Sold SOWs stay as designed finals** in the client's `00_Contracts/` (the only one in Drive: CauseCrazy, 2025-12-16). Rule added. `Lost` is empty. **Every SOW gets a link from its Notion Project** via the Contracts database (SOW → Project relation, Drive link on the Contracts row). Do this in the Drive → Notion linking step.
- **Strategy folders** (`Business Development/Company Strategy`, `Marketing/Marketing Strategy`, `Sales/Sales Strategy`) and probably `Product/` → **become Notion pages**, not Drive folders. They stay unmapped (untouched) until converted; then the empty folders get trashed.

### Still unmapped (to review after the inventory)
`Legal/Contracts/Unsigned`, `Client Projects/AI Advisory - All` (loose files), anything the Oct 7 map missed.

### Observations
- Creating Google files from CSV and markdown uploads works in one call (CSV → Sheet, markdown → formatted Doc). A markdown table imports with an empty header row, so use lists in CONVENTIONS.
- The connector can rename and trash folders; still can't move them.

## Next steps
- [ ] **JC:** paste the script into the migration sheet, run 0 → 1 (inventory). Then Claude reviews the inventory and fixes the rules.
- [ ] **JC:** run 2 (dry run), review the Plan with Claude, then 3 (execute), then 4/5 (empty folders).
- [ ] Convert the strategy folders (and probably `Product/`) into Notion pages, then trash the empty folders.
- [ ] Drive → Notion step: link every SOW to its Notion Project through Contracts.
- [ ] **JC:** move `XX_Logins` to a password manager and delete the folder.
- [ ] Update architecture Section 6 (drop `04_Offers`; Sales-Collateral; 04_Knowledge).
- [ ] Delete the `Taxonomy Test` folder once testing is done.
- [ ] Next build step: link Drive to Notion (Drive Folder URLs on Companies and Projects; Notion links in INDEX).
