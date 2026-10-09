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
The core offering is still **Information Taxonomy** (Roadmap → taxonomy design / migration → drift-checking → AI working-partner layer). It now has a concrete, generalizable **AI-native operating architecture**, built first for MOG and meant for any firm, eventually Blue Tusk itself: Notion as the working back end (eleven databases), Drive for finals, one ID per entity, agent rules, scripted backups, governance, and **skills in a git repo**. A free lead magnet built from it is drafted.

## Last worked on (2026-10-08)
- **Skills portability (AD-043 to AD-048):**
  - Tested: a Notion skill downloads as a clean open-standard `SKILL.md` folder, with attached files bundled. Claude does **not** find Notion-hosted skills on its own (readable by page ID only).
  - Decided: **a private git repo is the master**, laid out as a Claude plugin marketplace. Syncs automatically to Claude on Team plans and via Claude Code; manual upload on Pro (**Blue Tusk is on Pro**); one-way deploy to Notion AI (untested). Skills are written tool-agnostic and registered. Reference doc Section 8.1.
- **Navigation and training (AD-049 to AD-051):** no file tree in Notion, so Project pages act as folders, grouped "All work" views, a short sidebar hub, and find-by-ID. A literal folder tree exists only in the backup repo. Training (incl. SOPs) and a "How to use this system" quick reference page live in Notion Knowledge. Reference doc Sections 10.1 and 10.2.
- Earlier today: full reference architecture and decision log, commercial decisions (backup as paid offering, feature additions as ongoing role, free lead magnet), Handoffs database design, Blue Tusk Drive restructure proposal.

## Open / next
- **Sandbox is built** (all 3 phases) by Notion AI; spec revised to v2.1 from its feedback ([[20261008_notion-build-spec-sandbox]]). IDs in [[20261008_notion-sandbox-registry]]. Next: work the sandbox fix list in the spec, run the lock test (JC locks Projects, Notion AI tries a schema change), then write the migration spec for active work.
- **Set up Blue Tusk's own skills repo** as the template; move existing Claude skills into it.
- **Pending tests:** git → Notion skill deploy with a script (O-12); Notion AI using an enabled skill; Notion lock vs connector; backup → restore; Office file read cost; Sheets edit cost; Stripe webhooks.
- **Decide:** Blue Tusk on Claude Team for automatic skill sync (O-13); client skills repo ownership (O-11).
- **Lead magnet:** JC to edit; decide format, title, call to action, gating.
- **Blue Tusk Drive restructure:** confirm codes and structure; clean up `XX_Logins` (security).
- **Delete scratch Notion databases** when done: "SCRATCH - AI Drafts Test" and "SCRATCH - Skills Test".
- Still open from August: migration strategy, PE objections, naming the stack, reusable-IP vs billable split.

## Watch items
- **Drift-checking is bridge revenue;** platform AI will absorb it.
- **Cost-calculator math** ($325K–$375K/year) is illustrative only.
- **Token numbers** come from small internal tests; present as "in our tests."
- **The pasted web summary on Notion skills was partly wrong** (no documented GitHub → Notion upload, no ZIP import of skills). Check Notion's own docs before relying on claims.

## Key files
- [[20261008_ai-native-operating-architecture]]: **start here for the architecture** (skills: Section 8.1).
- [[20261008_ai-native-architecture-decision-log]]: decisions AD-001 to AD-054, open items O-1 to O-13.
- [[20261008_notion-build-spec-sandbox]]: the spec to paste into Notion AI (Phases 1–3).
- [[20261008_lead-magnet-ai-ready-workspace-draft]]: the free guide draft.
- [[20261007_google-drive-taxonomy-test-results]]: connector tests and token costs.
- [[business/projects/internal/google-drive-restructure/20261007_blue-tusk-drive-map-and-proposed-taxonomy]]: JC's Drive map and proposed structure.
- [[20260814_information-taxonomy-offering-stack]]: offering stack, moat, migration options.
