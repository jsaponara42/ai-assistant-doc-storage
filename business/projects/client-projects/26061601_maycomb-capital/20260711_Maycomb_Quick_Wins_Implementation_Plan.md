---
title: "Maycomb Capital — Quick Wins Implementation Plan"
date: 2026-07-10
tags: [client, project, task]
ai: claude
status: needs-attention
---

# Maycomb Capital — Quick Wins Implementation Plan

## Summary
Execution plan for Track A (QW-1 through QW-4) once the upsell closes. Roughly 5-6 weeks, sequenced by dependency, working the same way Blue Tusk already works with CauseCrazy: a shared task board, confirmation before starting each item, Maycomb provides access as needed, biweekly check-ins folded into the existing Roadmap Meeting rather than a new standing call.

## Context
Pricing and pitch sequencing for this track live in [[20260710_Maycomb_Upsell_Pricing_and_Pitch_Prep]]. Scope and impact reasoning for each item live in [[xx_Maycomb_AI_Automation_Roadmap_INTERNAL]] , Section 3. This document is the "how," not the "why" or the "how much."

---

## Working Model

- **Progress doc, not a live board.** One running doc, shared with Martina and Barry, updated every two weeks. No live check-in call by default, calls are available by request, not a standing part of this engagement.
- **Fixed update format, every time:**
  1. *Since last update* — what moved, however small.
  2. *In progress* — what's actively being worked.
  3. *Waiting on you* — anything blocked on Maycomb, named and dated.
  4. *Next* — what's coming in the following two weeks.
- **Quiet periods get reported honestly, not skipped.** If nothing shipped because an access request is still pending, that goes under "Waiting on you," dated. That's a real update, not an admission of nothing happening, and it puts any delay where it actually belongs.
- **Access:** Maycomb provides access as each item needs it, not all upfront. See per-item access lists below.
- **Documentation:** Every automation ships with a short plain-language SOP, what happens automatically, what needs a human, what must never be changed without looping in Blue Tusk. This also directly serves QW-4's institutional-resilience goal.

---

## Sequencing

QW-1 unblocks QW-2. QW-4 runs in parallel with everything, since it's governance, not a build. QW-3 is independent of QW-1/QW-2 and can start anytime access to the loan servicing model is confirmed.

**Week 1 — Kickoff + QW-1 + QW-4 governance activation start**
- Kickoff: confirm access needs across all four items in one conversation, not four separate asks.
- Build QW-1 (shared invoice mailbox). Low effort, no AI, mostly a SharePoint/mailbox configuration task Barry can execute directly or hand off.
- Start QW-4 in parallel: activate the Slack gripe list, confirm the monthly review slot on the Roadmap Meeting agenda, stand up the shared Projects library. This doesn't block on anything else.

**Week 2 — QW-1 goes live, QW-2 build starts**
- QW-1 live. Confirm with Varenka that the handoff into the new shared mailbox is clean before moving on.
- Start QW-2 (AP categorization) build, using QW-1's mailbox as the clean data source. Pull historical categorization decisions from the internal tracker or LeverPoint's records to ground the rules/prompt.

**Week 3 — QW-2 testing, QW-4 first live review**
- Run QW-2 against a live or recent AP cycle in parallel with the manual process, compare outputs before cutting over.
- Light LeverPoint touchpoint here is useful but not required for a first version, per the original scoping.
- QW-4's first monthly review happens at the Roadmap Meeting. Confirm the gripe list actually has entries to triage by this point.

**Week 4 — QW-2 live, QW-3 build starts**
- QW-2 goes live for the next AP cycle.
- Start QW-3 (auto-draft quarterly invoices). Needs structured or semi-structured read access to the loan servicing model and the invoice templates. Deal-team confirmation step and human send stay exactly as they are today, this automates the lookup and draft, not the approval.

**Week 5 — QW-3 testing**
- Run QW-3 against the next quarterly invoicing cycle in parallel with the manual process. ~15 borrowers, so this is a single real test cycle, not a long pilot.
- Confirm the deal team is comfortable with where the confirmation step sits in the new flow.

**Week 6 — Wrap-up**
- QW-3 live for the following quarter.
- Deliver the four plain-language SOPs.
- Final board review, mark everything closed, fold ongoing gripe-list triage into whatever comes next (Track D, if that's also sold).

---

## Access Checklist (ask for these as each item starts, not all at once)

- **QW-1:** SharePoint/mailbox admin rights or Barry's direct involvement. No client data access needed beyond what Barry already has.
- **QW-2:** Historical AP categorization decisions (internal tracker export, or LeverPoint records if Maycomb can request them). A short list of "known regular vendors and their categories" from whoever inherits Danielle's knowledge, ideally captured before she's fully gone.
- **QW-3:** Read access (or a structured export path) to the Excel loan servicing model. Current invoice templates. Confirmation from the deal team on how they want the confirmation step to work in the new flow.
- **QW-4:** Confirmation on the outstanding governance items already sent via the July 7 follow-up email (admin seat, Cowork/Code default-off, AI-owner arrangement, plan/billing, Fable caveat), plus write access to wherever the gripe list and Projects library should live (likely Slack + Claude Enterprise's Projects feature).

---

## Risk Notes

- **QW-2's biggest risk is timing.** Danielle's institutional knowledge of vendor categorization is the input the automation needs to train against. The sooner this starts, the better, every week that passes makes that knowledge harder to recover.
- **QW-3 depends on the loan servicing model's structure being workable for automated lookup.** Worth a quick technical look at the model before committing to the timeline above, if it's heavily manual/unstructured internally, QW-3 could run longer than a week to build.
- **QW-4 is the one item that can silently fail** if Martina and Barry don't actually close out the governance sign-offs. Worth chasing that explicitly in week 1 rather than assuming it happens in parallel.

## Next Steps
- Confirm this plan doesn't change once actual pricing/scope is agreed with Martina.
- Get the governance sign-off email closed out before or during week 1.
- Decide whether QW-1 (mailbox) is the free discretionary quick win per the SOW, if so, this plan's week 1 already covers it regardless of when the paid portion closes.
