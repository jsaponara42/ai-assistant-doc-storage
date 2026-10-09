---
title: "Product — Context Handoff"
date: 2026-10-09
tags: [handoff, project]
ai: claude
status: ok
---

# Product — Context Handoff

> Fresh-start note. Read this first. Only pull in the files linked below if the current task actually needs that level of detail — don't re-read everything by default.

## Where things stand
The architecture is designed (AD-001 to AD-059). The Notion half exists as a sandbox. **The Drive half is now built and migrated on Blue Tusk's real shared drive** (2026-10-09): client-first skeleton, INDEX (Sheet) and CONVENTIONS (Doc), all 726 old items moved by the migration script with 0 errors, old folders gone. **Next up is the MOG build plan (due to Martina Mon Oct 12)**; Blue Tusk's remaining build items follow after.

## Last worked on (2026-10-09)
- Built the Drive skeleton and migrated everything with a person-run Apps Script (agents can't move files). Strategy and offer docs became **15 pages in the sandbox Knowledge database** (Type = guide, Tags = strategy; `strategy` option added to Knowledge Tags with JC's OK); originals copied to `99_Archive/00_Company/Strategy-Originals`.
- Decided (AD-055 to AD-059): no Offers folder (offer sheets → `03_Marketing/Sales-Collateral`; templates → `04_Knowledge`); internal projects under `01_Clients/BTK_blue-tusk`; INDEX = Sheet; **one signed copy of each contract** in the client's `00_Contracts` (scope on the Notion Project, value on the restricted Contracts row); migration by script.
- Wrote the reusable **Drive migration playbook** and stored the script in the vault.
- Architecture Sections 5.5, 6 and 15 updated.

## Open / next
1. **MOG build plan for Oct 12** (see the MOG handoff note). Use the playbook and Blue Tusk run as the Phase 0 Drive template.
2. **Link Drive to Notion:** Drive Folder URLs on Companies and Projects; Notion links in INDEX (column J); each SOW linked to its Project through Contracts.
3. **Skills repo** (private GitHub, plugin-marketplace layout); first skill candidate: `drive-migration` (script + playbook).
4. **Scripts:** backup export, Last Contacted updater, Stripe webhook + reconciliation, drift checks. Decide where scripts run.
5. **Manual Notion steps:** sandbox fix list; restricted teamspace for Contracts/Invoices; **lock test**.
6. **Small items:** check whether one folder inside a shared drive can be restricted (for `00_Contracts`) before MOG.

## Watch items
- **Knowledge has an unexpected `Place` property** (seen after the 10-09 schema change; not in the spec). Ask JC before removing it, since removing a property is a destructive change.
- **Agents can't move Drive files;** use the migration script, or create in the right folder first time.
- **No backups where the Claude-connected account can see them.**
- **Notion pages for 5 long docs are summaries** (Landing Page, Quick Win, Meta Ads, Attraction Offers, Product Brainstorm); each links its full original.
- The drive restructure note's early sections predate today's decisions; the build log and architecture doc are current.

## Key files
- [[20261008_ai-native-operating-architecture]]: **start here** (Drive: Sections 5.5, 6; backups: 11; skills: 8.1).
- [[business/projects/internal/google-drive-restructure/xx_drive-migration-playbook]]: how to restructure and migrate a client drive; read before MOG's Drive work.
- [[business/projects/internal/google-drive-restructure/xx_drive-migration-script]]: the Apps Script source.
- [[business/projects/internal/google-drive-restructure/20261009_blue-tusk-drive-skeleton-build]]: Blue Tusk run log, decisions and key IDs (INDEX `1YVVuW421oLG-p_l8yv8Rxv_6ViLogVLLkJB7XgKBJq8`).
- [[20261008_ai-native-architecture-decision-log]]: AD-001 to AD-059, open items.
- [[20261008_notion-build-spec-sandbox]] and [[20261008_notion-sandbox-registry]]: Notion spec v2.1 and sandbox IDs.


## Update 2026-10-09 (afternoon): legacy Notion migrated; vault copy is next
- **The sandbox is now the live system.** Top-level page renamed "Operating System" (no longer "(Sandbox)"); example data removed by Notion AI.
- **Legacy Notion migrated** by Notion AI using [[business/projects/internal/product/20261009_Notion_OS_migration_prompts]]. Verified counts: Projects 26, Tasks 187, Companies 23, People 111, Meeting Notes 59 (pages moved, legacy database now empty), Contracts 5. JC checked all relations and trusts the current state.
- **Decisions added:** company Status "dormant"; Company Type "prospect" (no Client Code until promoted); "blocked" is its own Project Stage and Task Status, separate from Needs Attention; revenue fields live in restricted Contracts; existing project numbers kept (CFN-26061201, CCZ-25122101 closed, NWC 26061701 is a proposal).
- **Lessons and reusable checklist:** [[business/projects/internal/product/20261009_Notion_migration_lessons_learned]]. Use it as the playbook for MOG Phase 0.
- **Order agreed:** vault → Notion copy next, THEN the git backup script (nothing worth backing up until the data is in). Take a manual Notion export meanwhile. Vault stays intact as the archive until a backup restore drill passes.
- **Open in Notion:** Review list items (empty meeting types, Bill Kinnelly with no project, SyncScript lost vs done, "Add contacts to CRM" task); hide Source and Legacy Link on "All meetings"; remove Legacy Link properties after sign-off.
- **Next:** write the vault migration spec (inventory, dedupe, mapping to databases, batch plan), Claude copies through the Notion connector.
