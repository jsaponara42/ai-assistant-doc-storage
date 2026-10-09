---
title: "Product — Context Handoff"
date: 2026-10-08
tags: [handoff, project]
ai: claude
status: ok
---

# Product — Context Handoff

> Fresh-start note. Read this first. Only pull in the files linked below if the current task actually needs that level of detail — don't re-read everything by default.

## Where things stand
The AI-native operating architecture is designed (AD-001 to AD-054) and **the Notion half is built** as a sandbox in JC's workspace (Notion Business plan) by Notion AI, from the phased build spec (now v2.1). **Next session (2026-10-09): build everything the Notion spec left out**, starting with Google Drive, using JC's own Blue Tusk setup as the first real build and the template for MOG.

## Last worked on (2026-10-08)
- Notion AI built all 3 phases in "Operating System (Sandbox)". Its feedback and test answers produced spec v2 and v2.1. Database and data source IDs are in the sandbox registry note.
- Findings (AD-054): agent queries can't read formulas or rollups; search finds IDs in titles and text properties but not URLs; Notion AI can't lock databases; Created By shows the person; Notion AI didn't auto-load the enabled catch-up skill.
- Decided: project titles start with the Project ID (AD-052); skills live in a private git repo as master (AD-045 to AD-048); navigation via project-as-folder pages, find-by-ID, training and a quick reference in Knowledge (AD-049 to AD-051).

## Open / next: the out-of-scope list (spec's "Out of scope" section)
1. **Google Drive:** build the Blue Tusk skeleton (client-first, `00_Company` … `99_Archive`), CONVENTIONS and INDEX. Client and project folders follow `{CLIENT}_{slug}` / `{CLIENT}-{YYMMDDNN}_{slug}` with `client-sent/`, `in-progress/`, `delivered/`; client folders get `00_Contracts/`. **Agents can't move files,** so Claude builds the skeleton and JC drags content (or an Apps Script from a mapping table). First confirm client codes and top-level structure (drive restructure note), and clean up `XX_Logins`.
2. **Link Drive to Notion:** Drive Folder URLs on Companies and Projects; INDEX lists Notion links.
3. **Skills repo:** private GitHub repo laid out as a Claude plugin marketplace; move existing skills in; Claude Code marketplace (JC is on Claude Pro, so chat skills are manual uploads).
4. **Scripts:** backup export to markdown (folder tree by client/project in the backup repo), Last Contacted header-only updater, Stripe webhook plus nightly reconciliation, drift checks. Decide where scripts run.
5. **Manual Notion steps:** sandbox fix list in the spec; restricted teamspace for Contracts and Invoices (Business plan supports it); **lock test** (JC locks Projects, Notion AI tries a schema change).
6. **Then:** migration spec for JC's active work; MOG build plan.

## Watch items
- **Agents can't move Drive files;** create in the right folder first time.
- **No backups where the Claude-connected account can see them.**
- **The drive restructure note's update section predates `in-progress/`** (AD-038); the architecture doc is current.
- The pasted web summary on Notion skills was partly wrong; check Notion's own docs.

## Key files
- [[20261008_ai-native-operating-architecture]]: **start here** (Drive: Sections 3 and 6; backups: 11; skills: 8.1).
- [[20261008_notion-build-spec-sandbox]]: Notion spec v2.1, out-of-scope list, sandbox fix list.
- [[20261008_notion-sandbox-registry]]: sandbox database and page IDs.
- [[business/projects/internal/google-drive-restructure/20261007_blue-tusk-drive-map-and-proposed-taxonomy]]: current Drive map, proposed structure, client codes to confirm.
- [[20261008_ai-native-architecture-decision-log]]: decisions AD-001 to AD-054, open items O-1 to O-13.
- [[20261007_google-drive-taxonomy-test-results]]: what the Drive connector can and can't do.
