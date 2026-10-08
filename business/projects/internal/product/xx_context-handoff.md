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
The core offering is still **Information Taxonomy** (Roadmap → taxonomy design / migration → drift-checking → AI working-partner layer). On 2026-10-07 and 10-08 it gained a concrete, generalizable **AI-native operating architecture**, built first for MOG and meant for any firm, eventually Blue Tusk itself.
- **Notion holds** drafts, context, CRM, tasks and registers (ten databases).
- **Drive holds** finals and files.
- **The system rests on:** one ID per entity (`{CLIENT}-{YYMMDDNN}`), agent rules, a skills list, scripted backups and governance.

A free lead magnet built from it is drafted.

## Last worked on (2026-10-07 → 10-08)
- **Connector tests:**
  - **Google Drive passes** everything needed, except moving files and editing `.md` in place.
  - **Notion editing** measured roughly 15–200x cheaper than Google Docs.
- **Wrote the reference architecture and its decision log** (AD-001 to AD-041).
- **Commercial decisions:**
  - Backup and restore is an **ongoing paid offering** that creates stickiness (AD-039).
  - **Feature additions** are Blue Tusk's ongoing role, through the governance layer (AD-040).
  - **A simplified version becomes a free lead magnet** (AD-041), now drafted.
- **Mapped JC's own Blue Tusk Drive** and proposed a restructure:
  - Client first, then project.
  - 3-letter client codes built into project IDs.
  - Agents may work across a client's projects, never across clients.

## Open / next
- **Lead magnet:** JC to edit. Decide the format (PDF, Notion template, or both), the title, how specific the numbers are, the call to action, gating, and whether to merge it with the free-tier taxonomy guide.
- **Pending tests:**
  - Notion lock vs connector (JC locks "SCRATCH - AI Drafts Test" in the UI).
  - Backup → restore with relations.
  - Office file upload and read cost.
  - Sheets edit cost.
  - Billing webhooks (Stripe for Blue Tusk).
- **Delete the scratch database** when testing is done.
- **Blue Tusk Drive restructure:**
  - Confirm client codes and the top-level structure.
  - Clean up the `XX_Logins` folder (security).
  - Moves must be done by a human or a script, since agents can't move files.
- **Still open from August:**
  - Migration strategy (big-bang vs incremental).
  - Enterprise / PE objections not re-evaluated.
  - Naming the offering stack.
  - The reusable-IP vs billable split.
- **Later:** align JC's vault to client-first IDs (O-7); decide whether the backup git repo becomes the cloud vault (O-6).

## Watch items
- **Drift-checking is bridge revenue,** not permanent. Platform AI will absorb it.
- **The cost-calculator math** ($325K–$375K/year) is illustrative only. Verify it before any client-facing use.
- **The lead magnet's token numbers** come from a small internal test. Present them as "in our tests."

## Key files
- [[20261008_ai-native-operating-architecture]]: **start here for the architecture.**
- [[20261008_ai-native-architecture-decision-log]]: every decision and open item.
- [[20261008_lead-magnet-ai-ready-workspace-draft]]: the free guide draft.
- [[20261007_google-drive-taxonomy-test-results]]: all connector tests and token costs.
- [[business/projects/internal/google-drive-restructure/20261007_blue-tusk-drive-map-and-proposed-taxonomy]]: JC's Drive map and proposed structure.
- [[20260814_information-taxonomy-offering-stack]]: offering stack, moat, migration options.
- [[20260818_File_Taxonomy_Free_Tier_Principles]]: free-tier rules (lead magnet source).
- [[business/marketing/offers/20260814_file-chaos-marketing-angles]]: pain points and cited research.
