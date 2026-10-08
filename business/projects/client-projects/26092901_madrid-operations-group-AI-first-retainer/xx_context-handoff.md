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
The retainer is active: $1,500/month, Sep 29 – Dec 29. Discovery is done, and the current-state workflow map is built. **The target architecture is now fully designed** as a generalizable reference, with MOG as the first build. **JC owes Martina the build plan (Phases 0–1) on Monday, Oct 12.**

## Last worked on (2026-10-07 → 10-08)
- **Tested Google's connectors** and chose **Google Drive (D1)**.
- **Designed the full architecture.** See the reference doc; short version:
  - **Notion holds** drafts, client and project context, CRM, tasks, meeting notes, registers and the dashboard (eleven databases, including Handoffs).
  - **Drive holds** finals and files.
  - **Gamma** holds decks.
  - **QuickBooks + Wise** remain the source of truth for money; Notion keeps the register.
  - **Agents** work across a client's projects, never across clients.
  - **Backups** are scripted markdown exports.
  - **Schema changes** need approval.
  - **Skills** live in a private git repo (the master) and sync out. MOG is on Claude Team, so Claude picks them up automatically through organization sync. The deploy to Notion AI is untested (AD-043 to AD-048).
- **D9 is resolved:** drafts and context live in Notion. The per-client `_ai/` Drive folder is dropped.
- **Notion editing** measured roughly 15–200x cheaper than Google Docs. Scratch database: "SCRATCH - AI Drafts Test".
- **Drive project folders:** `client-sent/`, `in-progress/`, `delivered/`. Client folders get `00_Contracts/`. Client-facing files get clean titles.

## Open / next
- **Write the Oct 12 build plan.**
  - **Phase 0:** IDs and codes, Drive skeleton + CONVENTIONS + INDEX, Notion Companies / People / Projects / Tasks, System Registry.
  - **Phase 1 quick win:** CRM with Last Contacted / Next Follow-up (needs Martina's contact export), daily brief, Toggl trial.
- **Raise with Martina:**
  - One shared database across her clients (isolation by filters and agent rules).
  - Her Notion plan (Business is needed for unlimited SQL queries and teamspace permissions).
  - Who owns the system and backups, and Blue Tusk's access at the end of the engagement.
  - Client codes (MAY vs her "MC").
  - Who owns MOG's skills repo (Blue Tusk's GitHub or hers), and who is the Owner on her Claude Team plan (they connect the Claude GitHub App).
- **JC decides MOG's folder taxonomy** before suggesting anything specific.
- **The LFG loan admin list** is still outstanding.

## Watch items
- **Human gates:** Martina approves every send, every money decision and anything public. Ashley flags calendar conflicts and doesn't resolve them.
- **Agents can't move files in the shared drive.** Create files in the right folder the first time. How a file gets from `in-progress/` to `delivered/` is open (O-9).
- **Direct costs** (~$200/month) are paid by Martina; check with her before any recurring spend.
- **The Dec 29 auto-charge** would start month 4.
- **The Howie / Segway half of the 10/7 transcript** isn't filed yet.

## Key files
- [[business/projects/internal/product/20261008_ai-native-operating-architecture]]: **start here for anything architecture-related.**
- [[business/projects/internal/product/20261008_ai-native-architecture-decision-log]]: decisions AD-001 to AD-048 and open items O-1 to O-10.
- [[20261007_MOG_Current_State_Workflow_Map]]: MOG's workflows; the basis for the build plan.
- [[20261007_MOG_AI_Native_Stack_Architecture]]: the earlier MOG-specific draft. Its 10-08 update section says what's superseded.
- [[SOPs/20261007_MOG_First_Steps_Discovery]]: Martina's answers word for word.
- [[20260929_Madrid_Operations_Group_Client_Brief]]: background and problem register (P-001 to P-009).
