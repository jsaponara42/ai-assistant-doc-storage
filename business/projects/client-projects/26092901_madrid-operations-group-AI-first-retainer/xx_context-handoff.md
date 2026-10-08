---
title: "Madrid Operations Group AI-First Retainer — Context Handoff"
date: 2026-10-07
tags: [handoff, project]
ai: claude
status: ok
---

# Madrid Operations Group AI-First Retainer — Context Handoff

> Fresh-start note. Read this first. Only pull in the files linked below if the current task actually needs that level of detail — don't re-read everything by default.

## Where things stand
Retainer is active: $1,500/month, Sep 29 – Dec 29. Discovery is complete. Martina filled in the First Steps Google Doc, and she and JC went through it on a call on 10/7. The current-state workflow map is built. **JC owes Martina a build plan by Monday, Oct 12**, covering what he'll build and what he needs from her (logins, data exports).

## Last worked on (2026-10-07)
- Saved the completed discovery doc, with all comments, to `SOPs/`.
- Built the current-state workflow map: 8 workflows, human gates, call decisions, and a TO CONFIRM list.
- Call decisions:
  - A per-client context folder in MOG's system; drafts are written there and pushed to the client's system.
  - The build lives in the new MOG Claude Team account.
  - AI-agnostic design.
  - Google vs SharePoint is undecided, and both prefer Google.
  - BDR.ai and marketing are out of scope.
  - Toggl was suggested for time tracking.

## Open / next
- Write the Monday build plan. The quick wins are the Pipeline CRM with a follow-up cadence (needs Martina's exported contacts), a daily brief via scheduled task, and a Toggl trial.
- Google vs SharePoint: **decided 2026-10-07, Google**, after a hands-on connector test ([[business/projects/internal/product/20261007_google-drive-taxonomy-test-results]]). Test folder: "Taxonomy Test" in the Blue Tusk shared drive.
- The LFG loan admin list is still outstanding.
- **JC to decide MOG's folder taxonomy** before suggesting anything specific to Martina. Include a per-client `_ai/` folder (agent notes, handoff, markdown drafts).

## Watch items
- **`_ai/` storage is UNRESOLVED (D9).** Real `.md` files can't be edited in place in Drive. The interim plain-Google-Doc workaround has a recurring token cost JC wants to revisit before Phase 2. See the test log's UNRESOLVED section.
- Human gates: Martina approves every send, every money decision and anything public. Ashley flags calendar conflicts and doesn't resolve them.
- Client confidentiality: per-client separation must be built into the design.
- Direct costs (~$200/month) are paid by Martina; check with her before any recurring spend.
- Auto-billing: a Dec 29 charge would start month 4.
- The first half of the 10/7 transcript was about Howie and Segway, not MOG. It is not filed yet.

## Key files
- [[20261007_MOG_AI_Native_Stack_Architecture]]: target architecture draft v0.1 (5 layers, open decisions D1 to D8, build phases). Basis for the Oct 12 build plan.
- [[20261007_MOG_Current_State_Workflow_Map]]: the main reference for the build plan.
- [[SOPs/20261007_MOG_First_Steps_Discovery]]: Martina's answers word for word, plus comments. Open it for her exact wording or style examples.
- [[20260929_Madrid_Operations_Group_Client_Brief]]: background and problem register (P-001 to P-009). Updated 2026-10-07.
- [[client-facing-deliverables/20260929_SOW_Madrid_Operations_Group_AI_First_Retainer]]: open only for terms questions.


---

## Update 2026-10-08
**The architecture is now designed in full.** Read [[business/projects/internal/product/20261008_ai-native-operating-architecture]] (generalizable reference; MOG is the first build) and [[business/projects/internal/product/20261008_ai-native-architecture-decision-log]] (AD-001 to AD-037, plus open items O-1 to O-8).

**Short version:**
- Notion = drafts, context, CRM, tasks, registers and dashboard (ten databases).
- Drive = finals and files.
- Gamma = decks.
- QuickBooks + Wise = money (Notion keeps the register).
- One ID everywhere: `MOG-26092901`.
- Agents work across a client's projects, never across clients.
- Scripted markdown backups; schema changes only with approval.
- **D9 is resolved:** drafts and context live in Notion.

**Next:**
- Raise with Martina: one shared database across clients, her Notion plan, system and backup ownership, client codes.
- Turn Phases 0–1 into the build plan for Martina, due Monday, Oct 12.
- Pending tests: Notion lock (JC locks the scratch DB), backup → restore, Office file reads.
