---
title: "Maycomb Capital — AI & Automation Roadmap (DRAFT)"
date: 2026-07-07
tags: [client, project, strategy, deliverable]
ai: claude
status: needs-attention
---

# Maycomb Capital — AI & Automation Roadmap

**Prepared by Blue Tusk LLC**
**Prepared for:** Maycomb Capital (Martina Madrid Sebring, Interim/Fractional COO; Barry Porozni, IT)
**Date:** July 7, 2026
**Status:** FIRST DRAFT — content complete, not yet formatted/branded. Internal review copy for JC only; not for client distribution in this form.

> This is the core deliverable promised under the SOW ([[20260616_SOW_Maycomb_Capital_AI_Roadmap]]): a written AI Roadmap covering Maycomb's longer-term vision for AI and automation, prioritized automation opportunities ranked by ease of implementation and impact, and written recommendations. Branding pass (Blue Tusk palette/typography, per JC's July 7 decision) happens after content is locked. Internal-only commentary — strategy notes not meant for the client-facing version — appears in blockquotes marked **[INTERNAL]**.

---

## Executive Summary

Maycomb Capital enters its AI and automation journey at a pivotal moment: a fresh Claude Enterprise rollout, a full leadership transition (Ariella Rotenberg and Danielle Schweitzer both departing within weeks of each other), and a new interim fractional COO, Martina Madrid Sebring, stepping in to hold operational continuity. This roadmap turns six weeks of discovery — four documented back-office workflows, a completed workflow deep-dive, and a dedicated value-drivers conversation — into a concrete, sequenced plan.

Two things distinguish this roadmap from a typical back-office efficiency exercise. First, Maycomb's four core financial operations processes (legal bill tracking, the biweekly AP run, quarterly borrower invoicing, and annual budgeting) are now fully documented in Standard Operating Procedures — an unusually strong foundation that lowers automation risk and was captured just in time, before Danielle's and Ariella's institutional knowledge left with them. Second, this roadmap looks past pure cost-reduction to the actions that actually *drive value* for Maycomb — deal sourcing, borrower support, investor relations, and outcome-data collection — territory most automation engagements never reach because it isn't where people first look for automation.

**The recommendation is a two-track approach.** Track one is three low-effort, high-clarity quick wins that can be implemented almost immediately: a shared invoice mailbox that eliminates duplicate tracking with Maycomb's fund administrator, automatic expense-category classification for the AP run, and auto-generated first drafts of quarterly borrower invoices. Together these directly reduce the operational burden on Maycomb's finance function during its most vulnerable transition period, with minimal risk and no need for new institutional knowledge. Track two is a set of larger strategic investments — legal bill allocation automation, full cross-entity AP allocation, and a budget variance flagging and recommendation engine — that require more build time and coordination with Maycomb's fund administrator, LeverPoint, but deliver Ariella's explicitly stated top priority: compressing the quarterly budget-to-actuals review into a single short approval meeting.

Beyond the back office, this roadmap opens — but does not yet close — a third track: the value-driver opportunities surfaced directly by Ariella on July 7, 2026. Outcome-data collection for Maycomb's annual impact report is the clearest of these, and is promoted to a full problem statement below. Deal sourcing, investor relations, and borrower asset-management support remain open territory that Blue Tusk is well-positioned to explore further — this is the natural, high-value next phase of engagement, best undertaken as a paid, ongoing advisory relationship now that the free diagnostic scope is substantially complete.

Finally, this roadmap includes Maycomb's AI Playbook — the governance layer that determines whether any of the above gets adopted consistently across a 12-person team mid-transition, or fragments into inconsistent ad hoc practice. Overseeing that Playbook's rollout is itself a recommended next step, not a one-time deliverable.

---

## 1. Maycomb's AI & Automation Vision

> **[INTERNAL]** This section is written to eventually stand alone in the client-facing version — it's the "longer-term vision" piece explicitly promised in the SOW. Draft tone: aspirational but grounded, written for a 12-person team mid-transition, not a tech company.

Maycomb Capital's long-term AI and automation vision is not to replace judgment with automation, but to **stop wasting judgment on work that doesn't need it.** Maycomb's team — from the departing COO/CFO to the analyst who built a custom Excel loan servicing model from scratch — has consistently shown deep operational sophistication. The problem was never a skills gap; it was that too much of that sophistication was being spent on manual data entry, duplicate tracking, and recreating numbers that already existed somewhere else in the system.

The vision has three parts:

**1. Free up capacity for the work only a person can do.** Every process documented in this roadmap — legal bill allocation, the AP run, quarterly invoicing, budget variance review — has a mechanical core (data lookup, calculation, formatting) and a judgment core (does this allocation make sense given deal context, should we adjust this budget line, is this borrower relationship healthy). Automation should absorb the mechanical core so people spend their time on the judgment core.

**2. Build institutional resilience, not institutional dependency.** Maycomb is living through what happens when process knowledge lives in one or two people's heads during a leadership transition. The SOPs captured during this engagement are the first step; automating the mechanical steps within those SOPs is the second — so that the next transition (and there will be one) is far less disruptive.

**3. Extend the same discipline to revenue-driving work, not just cost centers.** Most firms stop their automation thinking at the back office. Maycomb's real differentiators — sourcing the right deals, supporting borrowers well, collecting and reporting outcome data with credibility — are just as automatable in their mechanical layers, and arguably more valuable to get right, since they touch investor confidence and mission delivery directly.

This vision is operationalized day to day through the **AI Playbook** ([[20260619_Maycomb_AI_Playbook_Long_Form]]), which governs how the team actually uses Claude, and through the roadmap below, which prioritizes what gets automated and in what order.

---

## 2. Current State Summary

*(Full detail in [[20260616_discovery-brief-maycomb-capital]] and [[20260624-Workflow-Map-Maycomb-Capital]]; this is a condensed orientation.)*

- **Organization:** Alternative asset manager / impact lender. Four LP fund vehicles, one single-member LLC, one two-member LLC management company. 12 full-time staff, based in Brooklyn, NY.
- **Leadership transition:** Ariella Rotenberg (COO/CFO) departed July 10; Danielle Schweitzer (Analyst) went part-time June 30. Martina Madrid Sebring is now the interim/fractional COO and primary engagement contact, alongside Barry Porozni (outside IT). A permanent Director of Finance & Ops and a new Analyst are being hired; a new Investor Relations hire starts August 3, 2026.
- **Documentation status:** All four core back-office processes are now captured as SOPs — Legal Bill Tracking, AP Run, Quarterly Borrower Invoicing, and Budget-to-Actuals (delivered July 7, 2026, completing the set). This is an unusually strong documentation baseline for a 12-person firm.
- **Technology stack:** Claude Enterprise (Haiku, Sonnet, Opus available), Excel/loan servicing model, LeverPoint (outsourced fund administrator — handles bank access and payment execution; Maycomb has no direct bank access by design), Affinity (CRM, replacing Salesforce), SharePoint, ShareFile, Slack, Teams (video only), DocuSign, Adobe, Expensify.
- **Claude rollout status:** Enterprise instance stood up the week before this engagement began. No standardization process yet for capturing and scaling effective usage patterns across the team — addressed by the AI Playbook (Section 6 below).
- **MSA/SOW status:** Signed July 7, 2026. Engagement fully authorized.

---

## 3. Automation Opportunity Register

Every opportunity below is scored on two axes:

- **Ease of Implementation:** Low (days, minimal coordination) / Medium (weeks, some cross-team or vendor coordination) / High (requires sustained vendor coordination and/or judgment-heavy edge cases)
- **Impact:** Low / Medium / High, based on time saved, risk reduced, and — for back-office items — how directly it reduces institutional-knowledge dependency during the transition; for value-driver items, how directly it touches revenue, investor confidence, or mission delivery.

Impact and effort estimates below are directional, based on the frequencies and time estimates captured during discovery — not final ROI figures. Each should be refined into a specific build estimate before a paid statement of work is scoped.

### Priority Grid (summary)

| Tier | Opportunity | Effort | Impact |
|---|---|---|---|
| **Quick Win** | Shared invoice mailbox (kill LeverPoint double-tracking) | Low | Medium |
| **Quick Win** | AP run expense category auto-categorization | Low–Medium | Medium |
| **Quick Win** | Auto-draft quarterly borrower invoices | Low–Medium | Medium–High |
| **Quick Win / Governance** | AI Playbook rollout (gripe list, SKILLS Phase 1, monthly review) | Low | Medium |
| **Strategic Investment** | Legal bill tracker rebuild (allocation rules engine) | Medium–High | Medium |
| **Strategic Investment** | Full cross-entity AP allocation automation | High | Medium–High |
| **Strategic Investment** | Budget variance flagging & recommendation engine | Medium–High | High |
| **Strategic Investment (needs scoping)** | Outcome data collection / impact report frictionless intake | Medium (once scoped) | High |
| **Exploratory (needs discovery)** | Deal sourcing & capital deployment | Unknown | Potentially High |
| **Exploratory (needs discovery)** | Investor relations & capital raising | Unknown | Potentially High |
| **Exploratory (needs discovery)** | Borrower asset management / portfolio support | Unknown | Potentially High |
| **Exploratory (needs discovery)** | Government / field-building relationships | Unknown | Medium–High (brand/mission value) |

---

### Quick Wins

#### QW-1 — Shared Invoice Mailbox (kill LeverPoint double-tracking)
- **Source:** P-003, workflow deep-dive (June 23–24).
- **Problem:** Maycomb maintains its own internal invoice tracker *and* LeverPoint maintains its own, purely so the two can be reconciled every AP cycle. This evolved historically and is now recognized as likely-redundant work.
- **Recommendation:** A single shared mailbox for incoming invoices, serving as the master record for both Maycomb and LeverPoint, eliminating the reconciliation step.
- **Effort:** Low. No AI required. Barry has already confirmed he can implement it (SharePoint/shared mailbox infrastructure is within his scope).
- **Impact:** Medium. Removes a structural redundancy, creates a single source of truth, and specifically eases Varenka's transition into running the AP run — she inherits one system instead of two. Also flagged by Danielle as important for vendor continuity (some vendors only have her personal email on file).
- **Dependencies:** None outside Maycomb/Barry. Does not require LeverPoint's cooperation to implement, though LeverPoint's workflow should be updated once live.

#### QW-2 — AP Run Expense Category Auto-Categorization
- **Source:** New, identified by JC (July 7, 2026), building on P-003.
- **Problem:** LeverPoint applies Maycomb's expense categories to each AP run invoice using an annually submitted budget. For known/regular vendors this works well; for new vendors, Danielle currently has to manually flag the correct category — a recurring judgment call that depends on her (soon to be departed) institutional knowledge of the business.
- **Recommendation:** Build a categorization layer — rules-based for the well-established regular-vendor patterns, with an LLM-assisted suggestion for new/ambiguous vendors — that drafts the expense category before the AP list reaches LeverPoint, working from the single source-of-truth mailbox established in QW-1. Reduces reliance on Danielle's memory of past categorization decisions and reduces back-and-forth with LeverPoint on miscategorized new vendors.
- **Effort:** Low–Medium. Requires access to historical categorization decisions (from the internal tracker or LeverPoint's records) to train the rules/prompt, plus a review step before send.
- **Impact:** Medium. Time saved is modest per AP run (10–20 invoices, biweekly), but the real value is removing a judgment-dependency bottleneck during the transition, and reducing the amount of back-and-forth correction currently required between Maycomb and LeverPoint.
- **Dependencies:** Best built after QW-1 (single mailbox as clean data source). Some coordination with LeverPoint likely useful, though not strictly required to build a first version.

#### QW-3 — Auto-Draft Quarterly Borrower Invoices
- **Source:** P-002, workflow deep-dive, plus JC's July 7 recommendation.
- **Problem:** Danielle currently pulls each borrower's accrued-interest figure from the Excel loan servicing model, copies the prior quarter's invoice, and updates dates/amounts — a process she described as most time-consuming in the model lookup itself, not the drafting. ~15 active borrowers, roughly 1 hour total once the deal team has confirmed figures.
- **Recommendation:** Auto-generate a first-draft invoice per borrower directly from the loan servicing model — pulling the correct accrued-interest figure, applying the correct template, and pre-filling dates — leaving only the deal-team confirmation step and a final human review/send. This is one of the most calculation-driven, lowest-risk processes in the entire register and a natural place to prove automation value early.
- **Effort:** Low–Medium. Requires structured (or semi-structured) read access to the loan servicing model and the invoice templates; the deal-team confirmation step and human send stay in place as safety checks.
- **Impact:** Medium–High. Removes the most time-consuming piece of a process expected to become more burdensome as the portfolio grows (some legacy borrowers aren't yet standardized onto the quarterly cadence). Low downside risk since a human still reviews and sends.
- **Dependencies:** Access/structure of the loan servicing model; deal-team workflow for confirming figures stays unchanged.

#### QW-4 — AI Playbook Rollout (Governance)
- **Source:** [[20260619_Maycomb_AI_Playbook_Long_Form]].
- **Problem:** Claude Enterprise was rolled out with no standardization process — some staff will become heavy "early adopters," others will barely use it, and inconsistent practice becomes harder to unwind the longer it runs.
- **Recommendation:** Activate the Playbook's lightweight loop: the gripe list (home: Slack), the monthly review (attached to the existing bi-weekly Roadmap Meeting), and Phase 1 of the SKILLS process (shared Projects library + a running "prompts that work" doc). Governance items (Cowork/Code default-off, AI-owner arrangement, admin seat, plan/billing confirmation, the Claude Fable cost caveat) need final sign-off from Martina and Barry — see [[20260707_Maycomb_Value_Drivers_Call_Prep]] for the outstanding list.
- **Effort:** Low to activate; ongoing light effort to sustain (the monthly review itself).
- **Impact:** Medium, compounding over time — this is what prevents every other automation in this roadmap from becoming "one person's tool" instead of a team standard.
- **Dependencies:** Governance sign-off from Martina/Barry (in progress via the July 7 follow-up email).

---

### Strategic Investments

#### SI-1 — Legal Bill Tracker Rebuild
- **Source:** P-001.
- **Problem:** Legal bills are manually logged, allocated across three scenarios (management company, fund, deal/borrower level), and tracked through payment/reimbursement — fully manual today, in Excel. Management-company and fund-level allocations are nearly 0% revision rate (rules-based, ready to automate); deal-level allocations run ~50% revision rate after deal-team review, since borrower-specific context often overrides the initial call.
- **Recommendation:** Replace the Excel tracker with a structured workflow that automates the two clean-cut allocation scenarios outright and routes deal-level bills through a structured deal-team confirmation step (rather than ad hoc cross-referencing conversations). Separately, build reimbursement tracking with automated reminders for the "Maycomb doesn't pay until reimbursed" gate — currently the single most friction-heavy piece of this process.
- **Effort:** Medium–High. The allocation logic itself is well documented (SOP delivered); the deal-level judgment loop needs careful design so it speeds up the ~50%-revision cases rather than just formalizing manual work.
- **Impact:** Medium. High-frequency (weekly) pain point for whoever inherits this from Danielle; reduces a "constant nudging" reimbursement-tracking burden specifically.
- **Dependencies:** SOP is complete; requires deal-team input to properly design the confirmation step.

#### SI-2 — Full Cross-Entity AP Allocation Automation
- **Source:** P-003 (beyond the QW-1 mailbox fix).
- **Problem:** The biweekly AP run must allocate bills correctly across four funds, a single-member LLC, and the management company. The mapping from bill to entity to payment source is mechanical once documented, but currently depends on institutional knowledge.
- **Recommendation:** Formalize the entity/allocation rules as an explicit rule set (SOP already delivered) and pilot automated or semi-automated allocation ahead of the AP run, coordinated with LeverPoint. Management approval and the two-approver Wells Fargo release stay in place as financial controls — this automates the allocation logic, not the controls.
- **Effort:** High. Requires sustained coordination with LeverPoint, since any process change to who tracks what touches their workflow directly.
- **Impact:** Medium–High. Removes a documented bottleneck (management-approval nudging currently stretches a 3-day cycle to a week) at the allocation-prep stage, and reduces institutional-knowledge dependency in a process that runs every two weeks indefinitely.
- **Dependencies:** LeverPoint cooperation; benefits from QW-1 and QW-2 being in place first.

#### SI-3 — Budget Variance Flagging & Recommendation Engine
- **Source:** P-004; **Ariella's explicitly stated top priority** for this engagement.
- **Problem:** LeverPoint's monthly budget-to-actuals report isn't accurate enough to act on directly. Maycomb does a manual quarterly deep review relying on Ariella's judgment rather than a defined process — she described wanting AI to run analysis through to a recommendation, not just flag data, with a goal of compressing review to a single half-hour meeting.
- **Recommendation:** Build a rules-based variance-flagging report against LeverPoint's monthly actuals (starting threshold discussed on the call: flag variances over 50% and $10,000 — to be confirmed with Ariella or her successor before build), then layer an LLM-generated narrative/recommendation on flagged items for human sign-off.
- **Effort:** Medium–High. The Budgeting SOP (delivered July 7, 2026) documents the process; the variance-threshold logic itself still needs confirmation from Ariella or whoever inherits budget ownership (likely Andi, per the SOP's approval structure).
- **Impact:** High. This is the single most explicitly requested outcome from the engagement's most senior internal champion — reducing a quarterly, judgment-heavy review to an approval meeting.
- **Dependencies:** Variance-threshold confirmation; Andi's ongoing budget-approval role; access to LeverPoint's monthly data feed.

#### SI-4 — Outcome Data Collection & Annual Impact Report (needs scoping)
- **Source:** P-007, identified July 7, 2026 (value-drivers call).
- **Problem:** Portfolio companies already track outcome data — Maycomb requires it as an underwriting prerequisite — but transferring that data into Maycomb's annual impact report (published end of Q1) is manual and, per Ariella directly, "such a difficult process" that "doesn't need to be" that hard.
- **Recommendation:** Design a more frictionless intake mechanism — a structured submission format or lightweight tool portfolio companies use to hand off data they already collect — while preserving live conversation for judgment calls. Not yet scoped in detail; the natural next step is a working session once Maycomb's new Investor Relations hire (starting August 3, 2026) is onboarded, since overhauling impact measurement/management is expected to be his first major project.
- **Effort:** Medium, once scoped — currently unscoped, which is itself the immediate next step.
- **Impact:** High. Touches investor confidence directly (the annual impact report is investor-facing) and reduces a described pain point at the source, rather than after the fact.
- **Dependencies:** Investor Relations hire's onboarding and initial assessment (starts August 3); this is a strong candidate for the first work item in a paid follow-on engagement.

---

### Exploratory — Value Driver Opportunities (Needs Deeper Discovery)

These four items were surfaced directly by Ariella on the July 7, 2026 value-drivers call and represent Maycomb's actual revenue- and mission-driving activity — deliberately looked at *in addition to* cost-center automation, since that framing is usually skipped. None are scoped enough yet to assign effort/impact with confidence; each needs a dedicated discovery pass. Full detail in [[20260616_discovery-brief-maycomb-capital]] Section 11.

- **VD-1 — Deal Sourcing & Capital Deployment.** Diligence process, two-person deal teams, the underwriting gate requiring borrowers to already have outcome-measurement systems, and "field-building" work with government bodies that drives brand value even without direct deals.
- **VD-2 — Borrower Asset Management / Portfolio Support.** Maycomb positions itself as "a lender that acts like a venture investor" — support intensity varies hugely by borrower, from low-touch to deeply hands-on financial support.
- **VD-3 — Investor Relations & Capital Raising.** A distinct workflow from deal sourcing — wholesale marketing/positioning, bespoke investor-specific sales process, structuring/closing, and ongoing relationship management.
- **VD-5 — Government / Field-Building Relationships.** Potential brand asset: a repeatable, easy-to-explain outcome-measurement system marketed as part of Maycomb's identity, floated but unscoped on the call.

> **[INTERNAL]** This is the clearest upsell hook in the entire roadmap. Nothing here can be responsibly scoped from a single conversation — that's the point. Recommend explicitly framing Section 5 (Next Steps) around this.

---

## 4. Recommended Phased Sequence

**Phase 0 — Complete.** Discovery, all four back-office SOPs, workflow map, AI Playbook draft, and this roadmap. Delivered under the free diagnostic engagement per the SOW.

**Phase 1 — Quick Wins (immediate, 2–6 weeks).** QW-1 through QW-4. Low effort, contained risk, directly reduces burden during the most vulnerable point of the transition (Varenka inheriting the AP run, the new Analyst onboarding by August). Strong candidates for either (a) the SOW's optional no-charge quick-win build, at Blue Tusk's discretion, to prove value ahead of a paid engagement, or (b) bundled as the first sprint of a paid Phase 2. **Decision point for JC — see Section 5.**

**Phase 2 — Strategic Investments (paid engagement, ~2–3 months).** SI-1 through SI-4. Requires sustained LeverPoint coordination and confirmation from Maycomb's finance leadership (Martina, Andi, and eventually the Director of Finance & Ops) on allocation and variance-threshold logic. SI-4 specifically should begin once the Investor Relations hire is onboarded (~August 3 onward).

**Phase 3 — Value Driver Discovery & Build (paid, ongoing advisory).** VD-1, VD-2, VD-3, VD-5. Begins with structured discovery sessions (likely with Martina and the deal team) to map these workflows the way Workflows 1–4 were mapped from SOPs, then sequenced builds as opportunities are validated.

**Ongoing — Governance.** AI Playbook oversight (gripe-list triage, SKILLS promotion, monthly review) runs continuously alongside all three phases above, ideally with Blue Tusk providing light oversight until the permanent Director of Finance & Ops is hired and can inherit the AI-owner role.

---

## 5. Recommended Next Steps

This engagement was delivered at no cost, as a diagnostic to identify where Blue Tusk can create real value for Maycomb. That value is now clearly identified — and clearly larger than what a free engagement can responsibly deliver.

**Two next-step recommendations:**

1. **Explore the value-driver opportunities more deeply.** VD-1 through VD-5 are the highest-potential, least-scoped territory in this roadmap — deal sourcing, investor relations, borrower support, and outcome-data collection all touch revenue and investor confidence directly, and none of them have been mapped the way the back-office workflows have. This is the natural, differentiated next phase: most automation engagements never get here.

2. **Oversee the AI Playbook's implementation.** A written playbook doesn't create adoption by itself, especially across a 12-person team mid-transition with no permanent AI owner yet in place. Blue Tusk continuing to lightly steward the gripe list, the SKILLS promotion loop, and the monthly review — until the Director of Finance & Ops is hired and can take over the AI-owner role — is both genuinely useful to Maycomb and a natural, low-friction way to stay embedded in the relationship.

**Decision point for JC:** whether to offer one Phase 1 quick win (most likely QW-3, auto-drafting quarterly invoices, given its low risk and clear time savings) as the SOW's discretionary no-charge build — to demonstrate concrete value before the upsell conversation — or to present all of Phase 1–3 together as a single proposed paid engagement. Recommend deciding this before the roadmap is finalized and sent, since it changes how Section 4 above should be framed for the client-facing version.

---

## 6. Appendix — Supporting Documents

- [[20260616_discovery-brief-maycomb-capital]] — full discovery brief, problem register, and value drivers (Section 11)
- [[20260624-Workflow-Map-Maycomb-Capital]] — current-state workflow spines for all four back-office processes, plus Workflows 5–8 placeholders for value-driver processes
- [[20260619_Maycomb_AI_Playbook_Long_Form]] / [[20260619_Maycomb_AI_Playbook_Cheat_Sheet]] — the governance layer referenced throughout Section 3 and Section 5
- `SOPs/` subfolder — all four source SOPs (Legal Bills, AP Run, Quarterly Invoicing, Budgeting)
- [[20260616_SOW_Maycomb_Capital_AI_Roadmap]] — governing Statement of Work
- [[20260707_Maycomb_Value_Drivers_Call_Prep]] — source material for Section 3's value-driver items and Section 6's outstanding Playbook governance questions
- [[xx_outstanding-questions]] / [[20260624_outstanding-questions-answered]] — full question/answer log across the engagement

---

## Open Items Before This Draft Is Client-Ready

1. Decide the Phase 1 quick-win framing (free discretionary build vs. bundled paid sprint) — see Section 5.
2. Confirm SI-3's variance thresholds (draft assumes >50% and >$10,000, per Ariella's own framing on the June call — needs sign-off from whoever inherits budget ownership).
3. Branding pass — Blue Tusk palette/typography, per JC's July 7 decision (this engagement is complimentary, so Blue Tusk's identity applies).
4. Strip or rewrite all **[INTERNAL]** blockquotes before this goes to Maycomb.
5. Executive Summary and Section 1 (Vision) should get a final tone pass once Section 5's positioning is locked — the upsell framing affects word choice throughout.
6. Confirm whether Martina and/or Barry should review a working draft before final polish, given they're now the primary engagement contacts.
