---
title: "Madrid Operations Group AI-First Retainer — Context Handoff"
date: 2026-10-08
tags: [handoff, project]
ai: claude
status: ok
---

# Madrid Operations Group AI-First Retainer — Context Handoff

> Fresh-start note. Read this first. Only pull in the files linked below if the current task actually needs that level of detail — don't re-read everything by default.

## Where things stand
The retainer is active: $1,500/month, Sep 29 – Dec 29. Discovery and the current-state workflow map are done. **The target architecture is fully designed** as a generalizable reference, with MOG as the first build. **JC owes Martina the build plan (Phases 0–1) on Monday, Oct 12.**

## Last worked on (2026-10-08)
- **Architecture, short version** (reference doc has the detail):
  - **Notion** holds drafts, context, CRM, tasks, meeting notes, registers and the dashboard (eleven databases).
  - **Drive** holds finals and files; **Gamma** holds decks; **QuickBooks + Wise** remain the money source of truth.
  - Agents work across a client's projects, never across clients. Backups are scripted. Schema changes need approval.
- **Notion build spec v2.1** is proven on JC's sandbox (built by Notion AI) and is the artifact for MOG's Notion build. Drive, scripts and the skills repo are being built on Blue Tusk first (from 2026-10-09) as the template.
- **Skills (new today, AD-043 to AD-048):** a private git repo is the master. **MOG is on Claude Team**, so Claude syncs skills automatically from the repo through organization settings. The deploy to Notion AI is untested.

## Open / next
- **Write the Oct 12 build plan.**
  - **Phase 0:** IDs and codes, Drive skeleton + CONVENTIONS + INDEX, Notion Companies / People / Projects / Tasks, System Registry, **skills repo connected to her Claude Team plan.**
  - Include a **"How to use this system" quick reference** and training pages in Notion Knowledge before the team starts (AD-051).
  - **Phase 1 quick win:** CRM with Last Contacted / Next Follow-up (needs her contact export), daily brief, Toggl trial.
- **Raise with Martina:**
  - One shared database across her clients.
  - Her Notion plan (Business for unlimited SQL and teamspace permissions).
  - Who owns the system, backups and **skills repo** (Blue Tusk's GitHub or hers), and Blue Tusk's access at the end.
  - Who is the Owner on her Claude Team plan (they connect the Claude GitHub App).
  - Client codes (MAY vs her "MC").
- **JC decides MOG's folder taxonomy** before suggesting anything specific.
- **The LFG loan admin list** is still outstanding.

## Watch items
- **Human gates:** Martina approves every send, money decision and anything public. Ashley flags calendar conflicts and doesn't resolve them.
- **Agents can't move files in Drive.** Create in the right folder first time; `in-progress/` → `delivered/` method is open (O-9).
- **Direct costs** (~$200/month) are Martina's; check before any recurring spend.
- **The Dec 29 auto-charge** would start month 4.
- **The Howie / Segway half of the 10/7 transcript** isn't filed yet.

## Key files
- [[business/projects/internal/product/20261008_ai-native-operating-architecture]]: **start here for anything architecture-related** (skills: Section 8.1).
- [[business/projects/internal/product/20261008_ai-native-architecture-decision-log]]: decisions AD-001 to AD-054, open items O-1 to O-13.
- [[business/projects/internal/product/20261008_notion-build-spec-sandbox]]: the Notion build spec (v2.1) to run for MOG.
- [[20261007_MOG_Current_State_Workflow_Map]]: MOG's workflows; the basis for the build plan.
- [[20261007_MOG_AI_Native_Stack_Architecture]]: earlier MOG-specific draft; its 10-08 update says what's superseded.
- [[SOPs/20261007_MOG_First_Steps_Discovery]]: Martina's answers word for word.
- [[20260929_Madrid_Operations_Group_Client_Brief]]: background and problem register (P-001 to P-009).
