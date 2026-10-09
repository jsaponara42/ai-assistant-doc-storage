---
title: "Blue Tusk Drive Skeleton — Build Log"
date: 2026-10-09
tags: [project, setup, tool, ai]
ai: claude
status: ok
---

# Blue Tusk Drive Skeleton — Build Log

## Summary
On 2026-10-09 Claude built the new client-first skeleton in the existing Blue Tusk shared drive: 70 folders, plus **INDEX** (Google Sheet) and **CONVENTIONS** (Google Doc) at the root. No existing files were touched. Old folders still sit beside the new ones; content moves are JC's drag-and-drop job.

## Context
Item 1 on the out-of-scope list in [[business/projects/internal/product/20261008_notion-build-spec-sandbox]]. Structure follows architecture Section 6 ([[business/projects/internal/product/20261008_ai-native-operating-architecture]]) and the Drive map ([[20261007_blue-tusk-drive-map-and-proposed-taxonomy]]). Blue Tusk is the template for MOG.

## Content

### Decisions (JC, 2026-10-09)
- **Client codes confirmed as proposed:** MOG, LFG, RFG, MAY, CAP, NWC, CCZ, EHM, RWR, SYN, PRC, BTK. (MAY vs Martina's "MC" still to settle with her.)
- **Built in the existing Blue Tusk shared drive,** beside the old folders, so drag-and-drop moves keep file links and IDs.
- **Internal projects get folders under `01_Clients/BTK_blue-tusk/`,** so every project ID resolves the same way.
- **INDEX is a Google Sheet;** CONVENTIONS is a Google Doc.

### Key IDs
- Shared drive root: `0ADcQ-34uTjUgUk9PVA`
- INDEX (Sheet): `1YVVuW421oLG-p_l8yv8Rxv_6ViLogVLLkJB7XgKBJq8`
- CONVENTIONS (Doc): `1r0WF8afiuA_IMbst4XSd17S_FIoszwY9vENnNLk3I-w`
- `01_Clients`: `1rGFgUrNlpmM8aAhRJWJPVhJCb6_0xusQ`
- **Every other folder ID is in INDEX** (columns: type, code, name, client, folder_id, contracts_folder_id, client_sent_id, in_progress_id, delivered_id, notion_link, vault_path, status, notes). INDEX is the source of truth; this note doesn't duplicate it.

### What was built
- **Top level:** `00_Company` (Admin, Legal, Finance → Bookkeeping / Receipts / Planning), `01_Clients`, `02_Pipeline` (Outreach, Partners, Proposal-Templates), `03_Marketing` (Brand-Assets, Content, Lead-Magnets), `04_Offers` (Strategy), `05_Knowledge`, `99_Archive`.
- **12 client folders** (11 external + BTK). Each external client has `00_Contracts/`.
- **7 project folders** with `client-sent/`, `in-progress/`, `delivered/`: MOG-26092901, LFG-26091801, RFG-26073101, MAY-26061601, CAP-26061201, NWC-26061701, CCZ-25121701.

### Not built yet
- **Project folders for EHM, RWR, SYN, PRC** (project dates unknown).
- **BTK project folders** (no internal project IDs assigned yet).
- **Notion links** in INDEX (column J) — item 2 on the out-of-scope list.

### Observations
- Creating Google files from CSV and markdown uploads works in one call: CSV → Sheet with data, markdown → formatted Doc. Cheap way to seed INDEX and CONVENTIONS for MOG too.
- The Sheet's tab came through named "Untitled"; the CONVENTIONS markdown table imported with an empty header row. Cosmetic.
- **CauseCrazy ID mismatch:** the vault folder is `20251221_cause-crazy`, but the old Drive folder says 20251217 and the ID used is `CCZ-25121701`. Needs JC to confirm.

## Next steps
- [ ] **JC:** drag content from the old folders into the new ones, then archive or delete the empty old folders. (Or Claude writes a mapping table for an Apps Script.)
- [ ] **JC:** confirm CCZ project ID (25121701 vs 25122101).
- [ ] **JC:** give project dates for EHM, RWR, SYN, PRC; Claude adds those folders and INDEX rows.
- [ ] **JC:** move `XX_Logins` contents to a password manager and delete the folder.
- [ ] **JC:** explain `AGP`, `GhostOps`, `Project Resources`, so they can be mapped.
- [ ] Delete the `Taxonomy Test` folder once testing is done.
- [ ] Next build step: link Drive to Notion (Drive Folder URLs on Companies and Projects; Notion links in INDEX).
