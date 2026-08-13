---
title: "Capital Financing — Context Handoff"
date: 2026-08-07
tags: [handoff, project]
ai: claude
status: ok
---

# Capital Financing — Context Handoff

> Fresh-start note. Read this first. Only pull in the files linked below if the current task actually needs that level of detail — don't re-read everything by default.

## Where things stand

Discovery phase, post-reset. Individual 1:1 deep-dive calls with Christy, Danielle, Yasmine, the FCs, and Howie are prepped (call-prep docs written, not yet all conducted). Yasmine's call already happened — her full post-underwriting process (Contracting/Funding/AR/Payoffs) is now mapped and has its own SOP. A call with Kaz (Salesforce architect) produced the single biggest finding of the engagement so far: the automation infrastructure for want #10 (consultant follow-up KPIs) already exists in Salesforce, built by Kaz and Josh, and is simply unused. Howie has also sent two rounds of detailed self-scoped wants (a wishlist + a structured inbox-automation brief) — his specs are getting notably sharper.

## Last worked on (2026-08-07)

- Ran Yasmine's live JB/Mighty walkthrough into the workflow map (new Workflow 6 — AR/Payoffs/close-out) and a full SOP, formatted to match `SOPs/20260728_Capital-Financing_Daily-Salesforce-Task-Review.md`.
- Logged the Kaz call: Opportunity + auto-task logic already built, unrolled (reframes wants #10/#15); confirmed IPR/Mighty↔SF flow, activity-tracking definitions, drip-campaign history, ~100-report glut; new want #19 (Slack + AI digest, Kaz's idea).
- Logged Julius's actual daily reports: concrete zero-substantive-reply count (160 sends/day), new LinkedIn-growth activity, and that Howie doesn't read Julius's own status reports.
- Logged want #20: Howie's fully-specified inbox-AI-assistant brief (hard constraint: no rules/folders). Cross-referenced its "wrong things route to me, not Christy" point into the existing Christy-authority-vacuum observation.
- Created `business/SOPs/2026-08-07-SOP-Discovery-Call-Prep-By-Role.md` — generalized, reusable method for building role-based call-prep docs (Executive/Ops/Sales templates).
- **⚠ Confidential, internal-only:** Kaz works full-time for Salesforce corporate and moonlights for Howie — never surface this in client-facing material.

## Open / next

- Conduct the actual 1:1 calls with Christy, Danielle, Yasmine (contracting call done), the FCs, and Howie — prep docs are ready and waiting in `call-prep/`.
- Get Yasmine's new SOP reviewed by her directly (`status: needs-attention` until confirmed).
- Resolve several `[TO CONFIRM]` items opened this session: case-expense fee mechanics past month 3, whether the paused Salesforce drips are the same tool as the historically-cancelled buggy one, non-standard file-assignment rule.
- Decide next steps on want #10 (rollout/adoption plan, not a new build) and want #20 (Howie's inbox assistant) — both are now well-scoped and ready to move on.
- Resolve the "Jan" reference (Julius/personal-assistant comparison) — still unconfirmed.

## Watch items

- Want #14 (referral portal): JC delegated the Jotform build to Christy's team — check whether that's actually been picked up; framed as low-risk specifically so it wouldn't stall.
- JC committed in writing to mapping everything Kaz built before recommending improve-vs-leave-as-is on the KPI dashboard — now partially fulfilled by the Kaz call, but the explicit recommendation back to Howie hasn't been delivered yet.
- Audrey and Victoria are named as actively resisting Howie's "approach not style" framing — relevant, sensitive context for their upcoming 1:1s; don't raise directly.
- JC's own weekend-email boundary (replies scheduled Sunday afternoon for Monday morning) is now stated in writing to Howie — hold it consistently.

## Key files

- [[xx_howies_wants]] — the master want-tracking doc, now at 20 ranked items plus Open Questions; read before any automation-scoping conversation.
- [[20260616-Workflow-Map-Capital-Financing-merged]] — the full process map; use the Quick-Reference Flowcharts section for a fast scan before diving into full detail.
- [[xx_Project_Learnings]] — relational/behavioral pattern log; check before any call involving Howie, Kaz, or the FCs.
- `call-prep/` — all prepped 1:1 questionnaires (Christy/Danielle/Yasmine, FCs, Howie).
- `SOPs/20260807_Capital-Financing_Contracting-Funding-AR-Payoffs.md` — Yasmine's role SOP, needs her review.
