---
title: "Ruthless For Good — Outstanding Questions"
date: 2026-08-18
tags: [client, project, task]
ai: claude
status: needs-attention
---

# Ruthless For Good — Outstanding Questions

Open questions and action items owed by Blue Tusk, surfaced from the 2026-08-18 email exchange between John-Carlos and Martina.

## Open Questions

1. **Outlook/M365 inbox assistant approach** — **Answered 2026-08-18:** Recommend the official **Claude for Outlook add-in** (beta, Pro/Max/Team/Enterprise) as the starting point. Bare minimum functionality: unread inbox triage (needs-you / Claude-can-handle / noise), draft replies/reply-alls/forwards landed **unsent** in the compose pane (never auto-sends — a good fit given the governance-first approach), thread summarization with citations, and calendar availability/scheduling assistance. This is distinct from the Microsoft 365 connector (broader, read-only by default, write tools available since July 2026 only if an admin turns them on) — recommend starting with the add-in specifically since it doesn't require Cowork or tenant-wide write access, only a per-user AppSource install. Sent to Martina 2026-08-18.
2. **Twintel tenant permissions** — Status of Martina's check with Twintel (RFG's IT vendor) on tenant permissions. Since the add-in route (Question 1) installs per-user via AppSource rather than needing tenant-wide write access, this may turn out to be a lighter lift than originally assumed — worth confirming with Martina once she's had a chance to loop in Twintel.
3. **Twintel contact details** — No named contact or direct line to Twintel yet; get this from Martina once relevant.
4. **Notion CRM skill** *(new, 2026-08-18)* — Concept floated: once the CRM schema exists (Master CRM Rebuild workstream), build a Claude Skill against Notion's official connector so contacts can be created/updated conversationally with automatic de-duplication and field mapping. Logged as a workstream in the discovery brief's Action Plan; not urgent but Aaron should be aware it's coming, since it's what actually removes the CRM data-entry burden rather than just relocating it.

## Action Items Owed by JC

- [ ] Send the AI usage governance document (in progress — Aaron's team wants to review this before turning on Claude Cowork; hard gate on widening tool access).
- [x] Give Martina a recommendation on the cleanest way to run an inbox/calendar assistant on RFG's Outlook/M365 setup (see Open Question 1) — sent 2026-08-18: Claude for Outlook add-in.
- [ ] Outline what a proper SharePoint restructure would involve on RFG's side, and what ongoing oversight it requires from Blue Tusk — timed to align with RFG's Fund II data-room prep.

## Notes

- Aaron holds final decision authority on how the engagement proceeds; Martina is the conduit bringing these items to him.
- See [[20260818_Discovery_Brief_Ruthless_For_Good]] for full context — Problem Register P-003 (governance) and P-005 (shared drive) and the revised Action Plan sequence.
