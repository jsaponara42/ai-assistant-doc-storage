---
title: "Product — Context Handoff"
date: 2026-10-09
tags: [handoff, project]
ai: claude
status: ok
---

# Product — Context Handoff

> Fresh-start note. Read this first. Only pull in the files linked below if the current task actually needs that level of detail — don't re-read everything by default. This one is longer than usual because 10-09 covered a lot of work.

## Where things stand
**Notion is now the live operating system, and it holds the real data.** The legacy Notion databases and the whole business vault have been copied in. Links between pages work, and JC has checked and trusts the current Notion state. **The vault still exists but has not been frozen yet**, and the skills still read and write the vault. Tomorrow: freeze the vault, repoint the skills at Notion, and put the migration spec into Notion. After that: the git backup script and restore drill. **The MOG build plan is due to Martina on Mon Oct 12** (see the MOG handoff).

## Current state of Notion (as of 2026-10-09 evening)
**Top page:** "Operating System" (`8ab9250c1af145c1ad1342caad9d1065`). It was the sandbox; it was renamed and the example data was removed. It holds 11 databases. Key data source IDs:
- Projects `0ac1daaa-95d2-41dc-8aef-44b1df153a21`
- Tasks `5c9d16fa-572b-469d-9aa1-79dfdf92e171`
- Companies `749074dd-9d7d-4009-8b47-841bb80d51fc`
- People `3fe77049-c03d-4160-a0ea-c46ae6639917`
- Knowledge `ea98a02b-12bc-40c4-8594-c9c32258464c`
- AI Drafts `d8ce42ea-1a58-4bfe-b65a-d01037c59942`
- Handoffs `ce596e39-248c-452c-ad3b-d8d99b4461ac`
- Meeting Notes `5edf424f-210a-40e4-9a02-e83011254981`
- Documents `ca0e33e9-2167-4f09-a234-6c4a04929809`
- Contracts and Invoices are restricted (admins only).

**System Registry** (`41a65693f0364e00b97884a521a71884`, in Knowledge). It covers the database index, relationships, change protocol and standard views. Its **change log is current through the wikilink pass**; append a row for every schema or content change.

**Legacy migration (done by Notion AI, verified):**
- **Counts:** Projects 26, Tasks 187, Companies 23, People 111, Meeting Notes 59 (pages moved in), Contracts 5. Every migrated row has a Legacy Link and a Migration log line.
- **Decisions:**
  - Company Status `dormant` and Type `prospect` (a prospect gets no Client Code until promoted).
  - `blocked` is its own Project Stage and Task Status, separate from Needs Attention.
  - Revenue fields live in restricted Contracts.
  - Project numbers are kept: CAP-26061201 is Capital Financing, now done; CCZ-25122101 is closed; NWC-26061701 is a proposal; LFG is lost.

**Vault copy (done):**
- **AI Drafts:** 176 business notes, all filed by project. Each has Project, Type, Audience, Status, Source Date, Vault Path and Summary.
  - Status: 84 published, 84 draft, 7 archived, 1 sent.
  - 83 are flagged Needs Attention for review.
- **Personal:** 18 notes on the private **Personal** page (`3f482a6d029a817b8532e0503ff40210`), outside the OS.
- **Evergreen areas:** the seven internal area projects were renamed without the quarter (Marketing, Sales, Admin, Systematize, Learning, Finance, Big Picture), and their IDs are unchanged. They are the permanent homes for reusable material.
- **Sprints:** tracked with the new **Sprint** select on Tasks (2026-q4, 2027-q1). Roll work forward by changing Sprint, not by moving it to a new project.
- **Wikilinks:** converted to Notion page mentions on 85 pages (645 rewrites). Links to 39 notes that weren't copied are plain text marked "(vault only)"; most are LinkedIn post-idea titles. Three pages that the importer had blanked were repaired by hand: the MOG handoff, this Product handoff, and the MOG current-state map.
- **Staging:** the "Vault import (staging)" page holds import duplicates. **JC is deleting it** (the connector can't trash pages).

**Still open in Notion:**
- Review list:
  - Empty meeting types.
  - Bill Kinnelly has no project.
  - SyncScript: lost or done?
  - "Add contacts to CRM" task.
- Hide Source and Legacy Link on "All meetings". Remove the Legacy Link properties after sign-off.
- Knowledge has an unexpected `Place` property. Ask before removing it.
- Restricted teamspace for Contracts and Invoices, plus a lock test.
- Review the 83 Needs Attention drafts over time.

## Last worked on (2026-10-09)
- Ran the legacy Notion migration with Notion AI using 6 prompts, then saved the lessons as a reusable checklist.
- Wrote the vault migration spec. Imported the vault with Notion's Markdown import (zips in the vault's `_notion-import/`, which git ignores), then set every page's properties through the connector.
- Converted the wikilinks and logged the results in the spec (section 4d) and the Registry change log.
- **Import lessons for MOG:**
  - The import is slow and leaves empty pages at first. Wait, or re-import a retry zip.
  - A late fill can reset titles. Re-check names afterwards.
  - Straight quotes become curly, so match on the curly ones.
  - Lines like `- [[note]]: text` get blanked. Rewrite them as `[[note]] — text` before zipping.
  - In tables, a pipe alias splits the cell.

## Open / next (in order)
1. **Confirm the staging page is deleted.**
2. **Freeze the vault:**
   - Add an "Archived — Notion is the source of truth (2026-10-09)" banner to the vault README.
   - Stop writing new notes to the vault.
   - Keep it as a read-only archive until a backup restore drill passes.
3. **Repoint the skills** (use `propose_skills`; read each current SKILL.md first):
   - `context-handoff` should read and write the project's handoff page in Notion AI Drafts, not `xx_context-handoff.md`.
   - `vault-mcp` should become archive-only, or be replaced by Notion guidance.
   - Check any other skills that write to the vault.
4. **Put the migration spec into Notion** (AI Drafts, Systematize). Refresh this Product handoff page in Notion as well.
5. **Git backup:** a scheduled Notion export script, a backup location the Claude-connected account can't see, and a restore drill. Only then retire the vault fully.
6. **MOG Oct 12 build plan.** This is separate but urgent; see the MOG handoff. Use the lessons checklist and the Drive playbook as Phase 0 templates.
7. Later: link Drive to Notion (Drive Folder URLs, INDEX column J, SOW to Contracts); set up the skills repo (first skill: `drive-migration`); scripts for Last Contacted, Stripe and drift checks.

## Watch items
- **Notion is the source of truth now. Don't create new vault notes**, even before the freeze is formal.
- **Change protocol:** add rather than rename or delete. Every change goes in the Registry change log.
- **The connector can't trash pages,** so JC deletes by hand. A failed `update_content` call applies none of its edits.
- **Vault MCP tools are now `mcp__remote-devices__vault__*`.** The device shell works on JC's Mac with the vault mounted.
- **MOG build plan due Mon Oct 12.**

## Key files
- [[20261009_Vault_to_Notion_migration_spec]]: mapping, decisions, import route, glitches and the wikilink results (sections 4–4d). Open it if anything about the copy looks off.
- [[20261009_Notion_migration_lessons_learned]]: the reusable checklist; use it for MOG Phase 0.
- [[20261009_Notion_OS_migration_prompts]]: the Notion AI prompts used for the legacy migration.
- [[20261008_ai-native-operating-architecture]]: **start here for architecture** (Drive: 5.5, 6; backups: 11; skills: 8.1).
- [[20261008_ai-native-architecture-decision-log]]: AD-001 to AD-059.
- [[20261008_notion-build-spec-sandbox]]: Notion spec v2.1.
- [[business/projects/internal/google-drive-restructure/xx_drive-migration-playbook]] — Drive migration method.
- [[business/projects/client-projects/26092901_madrid-operations-group-AI-first-retainer/xx_context-handoff]] — MOG state and the Oct 12 plan.
