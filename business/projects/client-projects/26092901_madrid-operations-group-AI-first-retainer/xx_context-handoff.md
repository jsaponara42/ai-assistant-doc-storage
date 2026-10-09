---
title: "Madrid Operations Group AI-First Retainer — Context Handoff"
date: 2026-10-09
tags: [handoff, project]
ai: claude
status: ok
---

# Madrid Operations Group AI-First Retainer — Context Handoff

> Fresh-start note. Read this first. Only pull in the files linked below if the current task actually needs that level of detail — don't re-read everything by default.

## Where things stand
Retainer active: $1,500/month, Sep 29 – Dec 29. Discovery and the current-state workflow map are done; the target architecture is designed. **JC owes Martina the build plan (Phases 0–1) on Monday, Oct 12; this is the next task.** As of 2026-10-09 the **Drive half is proven on Blue Tusk's own drive** (skeleton + INDEX + CONVENTIONS + script-based migration, 0 errors), so MOG's Phase 0 Drive work has a tested method.

## Last worked on (2026-10-09, on Blue Tusk; carries straight into MOG)
- **Drive migration method:** Claude designs and builds the skeleton; Martina's admin runs the migration script (inventory → Claude writes rules and checks them locally → dry run → execute → empty-folder cleanup). Takes about half a day plus inventory time.
- **New standards to carry into MOG:**
  - No Offers folder; offer sheets go in Marketing/Sales-Collateral, blank templates in Knowledge.
  - **One signed copy of each contract**, in the client's `00_Contracts`. Scope goes on the Notion Project; contract value goes on the restricted Contracts row.
  - Strategy and offer docs become Notion pages, not Drive files.
  - Credentials never go in Drive.
- Earlier (10-08): Notion build spec v2.1 proven on JC's sandbox; skills repo is the master; MOG is on Claude Team (automatic skill sync).

## Open / next
- **Write the Oct 12 build plan.**
  - **Phase 0:** IDs and client codes; Drive skeleton + CONVENTIONS + INDEX + **migration of her existing drive (playbook)**; Notion Companies / People / Projects / Tasks; System Registry; skills repo connected to her Claude Team plan; "How to use this system" quick reference and training pages (AD-051).
  - **Phase 1 quick win:** CRM with Last Contacted / Next Follow-up (needs her contact export), daily brief, Toggl trial.
- **Raise with Martina:**
  - One shared Notion database across her clients.
  - Her Notion plan (Business for unlimited SQL and teamspace permissions).
  - Who owns the system, backups and skills repo; who is Owner on her Claude Team plan.
  - Client codes (MAY vs her "MC").
  - **Who runs the migration script** (needs edit rights on her shared drive).
  - **Restricting `00_Contracts`** in a multi-person shared drive (check Google's current folder-restriction options first).
- **JC decides MOG's folder taxonomy** before suggesting anything specific; Blue Tusk's structure is the starting pattern, not the answer.
- **The LFG loan admin list** is still outstanding.

## Watch items
- **Human gates:** Martina approves every send, money decision and anything public. Ashley flags calendar conflicts and doesn't resolve them.
- **Agents can't move files in Drive.** Moves go through the script run by a person.
- **Direct costs** (~$200/month) are Martina's; check before any recurring spend.
- **The Dec 29 auto-charge** would start month 4.
- **The Howie / Segway half of the 10/7 transcript** isn't filed yet.

## Key files
- [[business/projects/internal/product/20261008_ai-native-operating-architecture]]: **start here for anything architecture-related** (Drive: 5.5, 6; skills: 8.1).
- [[business/projects/internal/google-drive-restructure/xx_drive-migration-playbook]]: how to restructure and migrate her drive.
- [[business/projects/internal/product/20261008_ai-native-architecture-decision-log]]: AD-001 to AD-059, open items.
- [[business/projects/internal/product/20261008_notion-build-spec-sandbox]]: the Notion build spec (v2.1) to run for MOG.
- [[20261007_MOG_Current_State_Workflow_Map]]: MOG's workflows; the basis for the build plan.
- [[SOPs/20261007_MOG_First_Steps_Discovery]]: Martina's answers word for word.
- [[20260929_Madrid_Operations_Group_Client_Brief]]: background and problem register (P-001 to P-009).
