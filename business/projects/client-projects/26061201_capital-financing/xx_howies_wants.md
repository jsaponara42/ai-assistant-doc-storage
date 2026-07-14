---
title: "Howie's Wants — Capital Financing"
date: 2026-07-14
tags: [client, project, strategy]
ai: claude
status: needs-attention
---

## Summary
Running list of things Howie (CEO, Capital Financing) has dictated that he wants built, changed, or explored — ranked by ease of implementation/feasibility. Sourced from a batch of voice-dictated transcripts provided 2026-07-14.

## Context
Howie pastes raw dictations over time. This doc captures each want in structured form, tagged to its source dictation, and ranks them so JC/Blue Tusk can prioritize. Items that read more like standard operating procedure (existing process description) than a "want" are flagged separately rather than folded into the ranked list.

## Content

### Ranked wants (easiest/most feasible → hardest/most involved)

| Rank | Want | Source | Description | Feasibility notes | Linked workflow map step(s) |
|---|---|---|---|---|---|
| 1 | Professional video content platform | Dictation #4 | JC to work with Howie creating short social-media video snippets. Wants a platform/setup that makes him look professional. | Lowest lift — mostly a tool + workflow choice (recording/editing platform) plus a light content cadence. No integration or org change required. | [[20260616-Workflow-Map-Capital-Financing-merged#Workflow 3 — Outbound Email & Social Cadence\|W3 Core Step 6 — Social Media Posting]] |
| 2 | Polished onboarding presentations & documents | Dictation #1 | A "foolproof" onboarding process from strategy call → onboarding, with a strong presentation for both stages, and documents with more class/polish than what Christie currently produces. | Mostly a design/content build (templates, deck, document polish) using existing tools. Feasible short-term once a workflow (strategy call → onboarding) is mapped. | [[20260616-Workflow-Map-Capital-Financing-merged#Sub-Step C — Case-Expense Onboarding Calls (sales-adjacent, currently broken)\|Shared Sub-Layer, Sub-Step C — Onboarding Calls]] |
| 3 | Client intake portal (replace "book"-length emails) | Dictation #1 | A link-based portal/form with user-defined click-and-play fields + document upload, feeding directly into their software or email, to replace law firms typing lengthy free-form emails. Howie believes case-submission friction is costing them business. | Medium — very buildable with a form tool (e.g., Jotform/Typeform-style), but requires defining the exact field set they actually need and wiring the output into existing intake (software or inbox). | [[20260616-Workflow-Map-Capital-Financing-merged#Sub-Step A — Document Collection (VA layer)\|Shared Sub-Layer, Sub-Step A — Document Collection]]; [[20260616-Workflow-Map-Capital-Financing-merged#Core Step 2 — Intake Collected\|W1 Core Step 2 — Intake Collected]]; [[20260616-Workflow-Map-Capital-Financing-merged#Core Step 2 — Case & Expense Details Collected\|W2 Core Step 2 — Case & Expense Details Collected]] |
| 4 | Automated conference-list splitting & assignment (Salesforce) | Dictation #2 | Automate importing/splitting the pre-conference attendee list once in Salesforce, assigning attendees to staff by territory, and using an AI agent to flag if a contact is already an active client / being managed by someone else (via last-activity lookup) before reassigning. | Higher complexity — needs Salesforce automation/admin work plus logic (and possibly an AI agent) to check active-client status before assignment. Depends on data quality of the "pre-conference list" and Salesforce records. | [[20260616-Workflow-Map-Capital-Financing-merged#Core Step 4 — Contact Loading & Segmentation\|W5 Core Step 4 — Contact Loading & Segmentation]]; [[20260616-Workflow-Map-Capital-Financing-merged#Core Step 5 — Assignment & Follow-Up\|W5 Core Step 5 — Assignment & Follow-Up]]; [[20260616-Workflow-Map-Capital-Financing-merged#Core Step 2 — Lead Assigned to Consultant\|W4 Core Step 2 — Lead Assigned to Consultant]] |
| 5 | Territory-based structure for financial consultants | Dictation #3 | Move FCs from "whole CRM/whole country" to defined state/regional territories (e.g., West Coast, Midwest, Brian on GA/NC/FL/LA, Howie covering remaining), with conference leads as the exception (an FC can pursue a lead they meet at a conference regardless of territory). Explicitly tied to hiring/economics discussion — Howie does not want to hire more people, and the cost structure to add headcount is atypical for this business. | Highest lift — this isn't a build, it's an org/operational restructuring with headcount and compensation-economics implications. Needs a separate operational/financial discussion with Howie before any implementation. | [[20260616-Workflow-Map-Capital-Financing-merged#Core Step 2 — Lead Assigned to Consultant\|W4 Core Step 2 — Lead Assigned to Consultant]]; [[20260616-Workflow-Map-Capital-Financing-merged#Sales Performance & Accountability Framework (CEO Directive)\|Sales Performance & Accountability Framework]] |

### Notes on ranking
- Rank reflects **build/implementation effort**, not business impact — the portal (#3) is likely Howie's highest-impact ask given his comment that submission friction is costing them business.
- #4 and #5 are related (territory assignment logic in #4 depends on the territory definitions being finalized in #5) — #5 should probably be resolved directionally before #4 is fully built out.

## Flagged Items

- **Dictation #5 is a verbatim duplicate of Dictation #1** (identical text, word-for-word — onboarding process + client portal). Not treated as a separate want; folded into items #2 and #3 above. Flagging in case this was an accidental double-paste or Howie re-dictated it intentionally for emphasis.
- **Dictation #2 partially describes an existing process rather than a want.** The first half (getting the pre-conference list, extracting emails, sending to Kaz for import, sending the Excel sheet out for someone to get emails, manually splitting to staff) reads like a description of the **current conference-list workflow** — it may belong in an SOP doc (there's already `SOPs/20260709_Capital-Financing_Conference-Process_SOP.md` in this project) rather than purely as a want. The actual "want" is the automation/assignment-logic layer on top of that process, which is what's captured in ranked item #4 above. Worth checking whether the existing Conference-Process SOP already reflects this description or needs updating.

## Next steps
- Confirm with JC whether Dictation #2's process description should be cross-referenced into the existing Conference-Process SOP.
- Prioritize #3 (portal) and #2 (onboarding polish) as likely first builds given effort vs. Howie's stated business-loss concern.
- Territory (#5) and its dependent automation (#4) need a separate economics/headcount conversation before scoping.
