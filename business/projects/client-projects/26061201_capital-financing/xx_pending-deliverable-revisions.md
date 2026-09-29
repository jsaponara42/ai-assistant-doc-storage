---
title: "Capital Financing — Pending Deliverable Revisions"
date: 2026-09-11
tags: [client, project, revisions]
status: collecting
---

# Pending Revisions — Opportunity Map (client-ready deliverable)

Running list of changes to the client-ready Opportunity Map, collected while reviewing the presentation, to be implemented together once the review pass is complete. Do not implement individually — wait for the go-ahead.

## Opportunity 3 — Slack + exception-based digest

1. **Reframe the core of this opportunity.** Center it on making it easy to update Salesforce contact touch logs in one place, not on a fully specified daily-briefing structure.
2. **Remove/soften the specific three-tier priority-list design** (opportunities needing attention / high-priority new contacts / lower-priority new contacts). Not a confirmed design yet — currently over-promises a decision that hasn't been made. Same applies to the mermaid diagram, which currently shows this structure explicitly.
3. **Keep, and keep prominent:** consultants logging consistently is the number one necessary thing. This stays as the anchor of the opportunity, unchanged.
4. **Add:** the automated report (calls, emails, KPIs) should go to the financial consultants themselves, not leadership only — for FC accountability, not just leadership visibility.
5. **Add:** opportunities should appear in the daily briefing/report in some form, but the design for how isn't decided yet. State this as a direction, not a structure.
6. **No change needed:** the AI-generated account summary mention — fine as written.
7. **No change needed:** the telephony system callout — fine as written.

## Opportunity 5 — Salesforce → MailChimp sync

1. **Reframe away from a specific tool.** "Salesforce → MailChimp sync" commits to a tool that may not be the right one — unclear whether MailChimp stays the answer or the incoming CMO ("Marketing Boss") handles this differently once in place. Generalize to: Salesforce holds the data needed to make warm outreach (scheduled marketing to existing/past clients, currently not working well) actually hit the right people. The underlying problem and the fact that Salesforce is the data source both stay — just drop the MailChimp-specific framing.
2. **Flag for the CMO, not just this map.** This should be on the incoming CMO's radar if it isn't already — note this as a handoff point, similar to other CMO-scope flags elsewhere in the doc.

## Opportunity 6 — Post-funding servicing/AR/payoffs, input to the Segue migration

1. **Status upgrade: this is now in progress, not just a migration-scoping placeholder.** The DOO (Christy) is actively scoping the fields and working directly with Segue to make sure the system works as expected at scale. She's explicitly taking the time to customize it properly rather than rushing, because of the scale Capital Financing operates at — getting the workflow right matters more than getting it fast. Reflect this as real, active progress, not a "still needs deciding" item.
2. **Keep the weaknesses list, and keep framing it as automation-relevant.** The documented weaknesses (no automated reminders, discretionary cadence, overlapping manual work, name-based reconciliation) stay — they're the requirements list feeding the Segue migration, and that framing is still the right one.
3. **New detail worth adding: Segue reportedly has a potential API integration**, which would open the door to different automations and AI-assisted work down the line. Worth naming as a reason this migration is worth doing well, not just a maintenance item.
4. **Connect this to the SOP work already in progress.** Christy's intake and underwriting SOPs (see Opportunity 7) and Yasmin's contracting SOP all feed into the same underlying structure the new system needs — spanning intake, underwriting, post-funding servicing, accounts receivable, and payoffs. Worth noting Opportunity 6 and Opportunity 7 aren't fully separate efforts; they're both inputs to the same Segue requirements structure.

## Opportunity 7 — Intake & underwriting structuring

1. **Status upgrade: Christy is actively working on this right now**, not just gated on her producing content at some future point. She's creating the SOPs that build out the structure, which forms the actual decision tree (rules-based hard checkpoints, described in the current write-up).
2. **Sequencing note:** once Segue is implemented, this decision tree is what gets mapped to actual automation — the SOP work now is the direct input to that later build, not a separate, disconnected effort. Worth stating this sequencing explicitly rather than leaving the SOP dependency as a vague "gated on" note.

## Opportunity 9 — Internal staff FAQ assistant

1. **Add to solution shape:** this probably lives in, or will live in, Claude — worth stating directly that it likely won't require any additional paid service or tool on top of what's already in place.

## Opportunity 10 — Outbound outreach automation

1. **Remove the MailChimp mention here too**, consistent with the Opportunity 5 note above — don't name a specific tool.
2. **New sub-item to add: centralized, approved email templates**, one per stage/motion, possibly living in SharePoint. Rationale: going from a blank page to a written email takes real time without a template, centralizing them makes them easier to manage and keep consistent, and AI can use a template as the base and write the case-specific customization on top of it. Flagged as a genuinely quick, low-effort piece of this opportunity — worth including, though not confident it should be elevated all the way to its own Quick Win tier. Leave as a sub-point within Opportunity 10 rather than a separate numbered opportunity unless told otherwise.

## Opportunity 11 — Conference list matching & territory structure

1. **Downgrade this from "Needs Decision First."** Not urgent, not super high value right now — more of a longer-term item. The opportunity itself is understood and real, but the manual cost today is acceptable and probably cheaper than building full automation for it, especially since every conference list arrives in a different format. Reconsider whether this stays a headline numbered opportunity or moves to the backlog appendix given the lower priority.
2. **New idea, possible smaller near-term win:** rather than automating the full match-and-assign process, have Claude take a raw conference list and normalize/standardize it into a consistent view first, which the Salesforce Administrator (Kaz) could then upload and work with more easily. This is a smaller, more targeted fix than full automation, worth calling out separately from the bigger unresolved territory-structure question.

---

*(add further notes below as the review continues; implement all at once when told to proceed)*
