---
title: "Maycomb Capital — Discovery Call Brief"
date: 2026-06-16
tags: [client, project]
ai: claude
status: needs-attention
---

# Maycomb Capital

Alternative asset manager / fund manager operating a management company structure over multiple fund vehicles, with an outsourced fund administrator handling back-office fund accounting.

**Primary internal contact:** Ariella Rotenberg — COO/CFO, arotenberg@maycombcapital.com
> ⚠️ NEEDS INPUT: Ariella's phone and mobile.
> ⚠️ NEEDS INPUT (task, not gap): Capture Ariella's personal/forwarding contact info before her July 10 departure to retain the relationship. Ariella was out the week of the workflow deep-dive call (June 23–24) — follow up on return.

---

## 1. Client and Organization

- **Name:** Maycomb Capital.
> ⚠️ NEEDS INPUT: Confirm legal entity name(s) and any trade name, if different from "Maycomb Capital." *(Reserve for Ariella session.)*
- **Headcount:** 12 full-time people.
- **Corporate structure:** Four limited partnership vehicles (the funds), one single-member LLC, and a two-member LLC that serves as the management company / operating business. Business matters are run through the operating company for operational and financial simplicity; expenses and revenue are generated primarily by the fund entities and a little by the single-member LLC.
- **Principal contact for this engagement:** Ariella Rotenberg, COO/CFO *(inferred from context — she speaks to AP runs, budget-to-actuals, and cash management with CFO-level ownership)*. Email: arotenberg@maycombcapital.com.
- **Connection source:** Introduced by Barry Porozni (mutual connection, also does Maycomb's IT).
> ⚠️ NEEDS INPUT: Barry's exact title and contact details. Confirmed on the workflow deep-dive call (June 23–24): outside IT vendor (not internal staff). IT scope includes SharePoint, shared mailbox infrastructure, and Claude Enterprise admin controls — Barry affirmed the recommendation to disable Cowork and Claude Code by default at the org level.

---

## 2. Business Profile

Maycomb Capital is an alternative asset manager that lends to portfolio companies/borrowers through a multi-fund structure (four LP vehicles plus a single-member LLC), with a separate two-member LLC management company functioning as the operating business. The fund entities and single-member LLC generate the revenue and expenses; the management company runs all the business matters and pays the bills, requiring an internal cross-entity allocation system. Maycomb appears to operate in an impact or mission-aligned lending space — borrowers are tracked against outcome metrics tied to grants or government-linked reporting (self-reported by borrowers, with deal teams providing high-touch oversight, sometimes supplemented by outsourced tracking).

Maycomb outsources core fund administration (fund accounting, AP run estimates, draft budget-to-actuals) to **LeverPoint** (their fund administrator, also referred to as "Ultimis" interchangeably by the team). LeverPoint handles bank account access and payment execution — Maycomb has no direct bank access by design, as a cash control measure. The team describes LeverPoint as having become reliable after past turnover required restarting processes. Maycomb just stood up an enterprise Claude instance the week of this call, with a fresh, evolving set of internal usage guidelines — the engagement enters at the very beginning of Maycomb's formal AI adoption, before any strategic roadmap has been built around it.

The business is in a leadership transition: both COO/CFO Ariella Rotenberg and Analyst Danielle Schweitzer are exiting within weeks of this call (see Section 4), creating urgency to document standard operating procedures before institutional knowledge leaves with them. The engagement entered via referral (Barry Porozni connecting John-Carlos to Maycomb) and is structured as a free, in-kind discovery/diagnostic engagement, with the expectation of a paid scope of work if it expands beyond the initial engagement.

---

## 3. Goals

**Personal Goals**
- Danielle Schweitzer: wants the back-office burden (legal bill tracking, manual invoicing, budget reconciliation) automated so she — or whoever succeeds her — can focus on big-picture planning instead of "the nitty gritty." She explicitly wants to leave Maycomb better than she found it for the people taking over her responsibilities.
- Ariella Rotenberg: similar — wants the AP run / cash allocation complexity and budget-to-actuals analysis to require less manual, expert-level judgment so the business is less dependent on one person's "intimate knowledge."

**Business Goals**
- Build a strategic roadmap for AI/automation adoption at Maycomb, beyond the current "open sandbox" Claude rollout — get ahead of "do's and don'ts" before bad habits form.
- Standardize whatever automation/AI usage patterns are found to work, so that early-adopter behavior doesn't fragment into inconsistent practices across the 12-person team.
- Use the transition (both Ariella and Danielle departing) as an opportunity to formalize SOPs that the incoming fractional COO, Director of Finance & Ops, and Analyst can inherit cleanly.
- Possibly extend automation engagement to portfolio companies that struggle with their own outcome-reporting processes.

---

## 4. Key People — Internal

### Ariella Rotenberg — COO/CFO
- **Working Style:** Strategic, systems-minded; speaks with precise command of cross-entity financial mechanics (AP allocation, cash management, budget-to-actuals). Thinks in terms of automatable decision rules (e.g., flag variances over 50% and $10,000) and wants AI to run analysis through to a recommendation, not just flag data — minimizing review time to something like a single half-hour meeting.
- **Tenure / Transition:** Last day confirmed as July 10. Will continue afterward as a senior advisor.
- **Owns:** AP run / cash allocation across entities, budget-to-actuals analysis, overall financial operations strategy.
- **Relevance:** Primary internal champion and likely main point of contact for the engagement; departing but staying on in an advisory capacity, so continuity risk is partially mitigated.
- **Contact:** arotenberg@maycombcapital.com.
> ⚠️ NEEDS INPUT: Phone and mobile.
> ⚠️ NEEDS INPUT: Personal/forwarding contact info to capture before July 10 departure, to retain the relationship.

### Danielle Schweitzer — Analyst
- **Working Style:** Hands-on, detail-driven; manually executes the legal bill tracking and quarterly borrower invoicing in Excel. Candid about pain points ("pile it on") and motivated to document/automate processes before she leaves so successors don't inherit the same grind.
- **Tenure / Transition:** Last full-time day is **Monday June 30** (corrected from June 29). Part-time through July and August, then intends to stay involved in this engagement when she returns part-time. Has explicitly said she won't disappear.
- **Owns:** Legal bills tracking process (Excel-based), quarterly borrower invoicing for interest and principal payments, investor correspondence (capital account statement questions), deep manual review supporting the quarterly budget-to-actuals analysis.
- **Relevance:** Richest source of process detail for this engagement; a flight risk to institutional knowledge if SOPs aren't captured before her part-time period ends in August. Three SOPs delivered as of the workflow deep-dive call — see Section 6 / P-006.
- **Contact:** dschweitzer@maycombcapital.com.
> ⚠️ NEEDS INPUT: Phone and mobile.

### Barry Porozni — IT (outside vendor)
- **Working Style:** Present on the workflow deep-dive call (June 23–24) alongside Danielle. Participated actively — flagged the shared mailbox as a quick-win infrastructure improvement and agreed to help implement it (SharePoint, shared mailbox setup). Affirmed the recommendation to disable Cowork and Claude Code at the org level for cybersecurity reasons.
- **Relevance:** Mutual connection who introduced John-Carlos to Maycomb; handles Maycomb's IT as an outside vendor. Scope confirmed to include: SharePoint, shared mailbox/storage infrastructure, and Claude Enterprise admin controls.
- **Contact:** Not yet captured.
> ⚠️ NEEDS INPUT: Barry's exact title, company name, and contact details. Also confirm: who holds the Claude Enterprise admin seat and what controls are currently configured (global toggle, group restrictions).

### Incoming roles
- **Interim fractional COO** — to hold strategic initiatives during the transition. Status unknown — reserve for Ariella.
- **Director of Finance and Ops** — planned full-time hire to succeed much of Ariella's and Danielle's combined scope. Timeline unknown — reserve for Ariella. This role is the intended permanent holder of the AI-owner role.
- **Analyst (finance and ops)** — Maycomb is actively hiring. Danielle expects the new analyst to be fully onboarded by August and intends to personally transition them.
- **Varenka (office manager)** — confirmed interim operations lead. Taking over the AP run and being looped into broader operations. Named by Danielle as the interim AI owner and process champion until the Director of Finance & Ops is hired. Also identified as interim approval holder for AP run sign-offs (alongside Miljana) after Ariella's departure.
- **Miljana** — named as one of the people who will handle AP run approval sign-offs after Ariella leaves. Described as having deeper business knowledge in certain areas.
> ⚠️ NEEDS INPUT: Timeline for interim fractional COO and Director of Finance & Ops hires. Confirm whether engagement should plan to onboard them directly once in place.

---

## 5. Key People — External (Vendors & Partners)

### LeverPoint (outsourced fund administrator)
- **Role:** Handles fund accounting across all of Maycomb's entities; generates AP run estimates and a draft monthly budget-to-actuals report that flows from the general ledger. Critically: LeverPoint holds bank account access and executes all payments — Maycomb has no direct bank access by design (cash control).
- **Current state:** Described as having become reliable after a period of staff turnover. Maycomb still manually reviews and adjusts their output. Currently receives all invoices from Danielle (forwarded one by one), maintains their own tracking list, and sets up payments bi-weekly. Also referred to as "Ultimis" by the team — may be a historical name or platform name.
- **AP run mechanics:** Maycomb sends invoices to LeverPoint, LeverPoint tracks them, sends back a reconciliation list every two weeks, Maycomb compares against their own tracker, resolves discrepancies, then seeks management approval before instructing LeverPoint to release payments.
- **Relationship to engagement:** A required collaborator for any AP run or budget-to-actuals automation. Any process change (e.g., Maycomb tracking allocations internally and sending a single approved list directly) involves LeverPoint.
> ⚠️ NEEDS INPUT: LeverPoint primary contact name. Confirm with Ariella whether LeverPoint should be looped into the engagement directly.

### Barry Porozni — IT (outside vendor)
- Confirmed outside IT vendor (not Maycomb staff). Functions as both a personal connector and Maycomb's outside IT vendor. Scope confirmed to include: SharePoint, shared mailbox/storage infrastructure, and Claude Enterprise admin controls. Present and participating on the workflow deep-dive call.
> ⚠️ NEEDS INPUT: Exact title, company name, and contact details. Confirm who holds the Claude Enterprise admin seat and what controls are currently configured.

---

## 6. Technology Stack

### Claude (Enterprise instance)
- **What it is:** Enterprise Claude instance, set up by Danielle the week prior to this call, intended as Maycomb's primary AI tool.
- **Current state:** Freshly deployed ("open sandbox") with a draft set of usage guidelines expected to evolve monthly/quarterly. No strategic plan yet for proactive, function-specific use — staff have access but no structured direction on how to leverage it for actual workflow improvement.
- **Models available:** Haiku, Sonnet, and Opus — all three confirmed accessible in their enterprise plan.
- **Admin:** Cowork and Claude Code recommended to be disabled at the org level by default (cybersecurity — both access the terminal). Barry affirmed this. Confirm with Barry who holds the admin seat and what is currently configured.
- **Gap:** No standardization process yet for capturing and scaling individual employees' successful use patterns across the 12-person team.

### Excel / Loan Servicing Model
- **What it is:** Primary tool for legal bill tracking (manual log of incoming bills, payment status, and which fund/borrower they're allocated to). Also the basis for a custom-built internal **loan servicing model** — an Excel workbook with a tab per borrower tracking all cash flows and accrued interest. This is the source of truth for quarterly borrower invoice amounts.
- **Current state:** Fully manual. Legal bill tracker described as a pain. The loan servicing model was built by Danielle specifically to give Maycomb internal visibility, since they didn't want to rely solely on LeverPoint's tracking.
- **Loan servicing software:** Maycomb evaluated dedicated loan servicing software (with borrower portal and auto-invoicing) but put it on hold due to the leadership transition. Estimated approximately one year out.

### Affinity (CRM)
- **What it is:** New CRM, recently selected after a full evaluation process, replacing Salesforce. Official onboarding just started at the time of this call.
- **Current state:** Salesforce was very underutilized — described as "not the right fit." Affinity is expected to become a major part of day-to-day operations once fully onboarded.

### LeverPoint (fund administrator platform)
- See Section 5 — External Vendors. LeverPoint handles fund accounting, AP run payment execution, and maintains their own invoice tracking. Maycomb does not have direct bank access.

### SharePoint
- **What it is:** Document storage platform, in use. Also a candidate for shared mailbox / invoice storage infrastructure under the proposed AP run process improvement.

### ShareFile
- **What it is:** Secure file sharing tool, in use. Likely used for external sharing with LeverPoint, legal vendors, and others.

### Slack
- **What it is:** Primary internal messaging and collaboration tool. Used for deal-specific channels and formal internal comms.
- **Current state:** Sticky — the full team has resisted moving to Teams despite Maycomb paying for it. Identified as the home for the **gripe list**. Anonymous posting is available but not required.
- **Roadmap meeting:** Bi-weekly meeting confirmed as the right venue for surfacing and actioning gripe list items.

### Microsoft Teams
- **What it is:** In use for video calls only. Maycomb pays for Teams but the team has not adopted it for messaging — Slack remains the de facto tool.

### DocuSign
- **What it is:** E-signature platform, confirmed in use.

### Adobe
- **What it is:** In use (likely Acrobat or similar) — relevant to PDF handling of legal bills and invoices.

### Expensify
- **What it is:** Employee expense reporting platform. Team members with company credit cards submit expenses through Expensify; expenses go through the same allocation process (expense category) and are approved by their manager monthly.

### General Ledger (managed via LeverPoint)
- **What it is:** Central financial record fed by the AP run; underlies both the budget-to-actuals reporting and the cash/revenue allocation across entities.
- **Current state:** Maintained by LeverPoint; Maycomb receives draft output monthly but does not treat it as accurate enough to act on directly — requires manual quarterly deep review by Danielle and Ariella.

---

## 7. Problem Register

### P-001 — Legal Bill Tracking and Allocation (Processes)
- **Area:** Processes / Tools.
- **Problem:** Legal bills arrive from outside counsel and must be manually logged in Excel, then manually allocated to the correct fund or borrower, tracked for incoming payment (sometimes from a borrower), and tracked again to confirm Maycomb pays the bill once reimbursed. This is fully manual, cross-referencing conversations with colleagues to determine responsibility, and described by Danielle as her least favorite recurring task.
- **Current Thinking:** This is treated as a bespoke, judgment-heavy process because it spans multiple funds and payment-responsibility scenarios, so it has stayed in Excel rather than being systematized.
- **Reframe:** The allocation logic (which fund/borrower, payment-then-reimbursement sequencing) is a rules-based workflow that can be encoded once and applied consistently — it doesn't require fresh judgment each time, only correct intake and tagging.
- **Approach:** Map the full bill lifecycle (intake → allocation → payment tracking → reimbursement tracking) and build a structured tracker/workflow to replace the Excel process. Status: SOP delivered by Danielle. Workflow deep-dive completed (June 23–24).
- **Key findings from workflow deep-dive:**
  - Legal bills arrive approximately **weekly**.
  - Three allocation categories, each with different escalation needs:
    1. **Management company** — immediately determinable by Danielle; essentially 0% revision rate.
    2. **Fund responsibility** — also relatively clear; paid by management company, then allocated/reimbursed quarterly by the fund. Exception: Fund Two has hit a legal fee cap in a specific category, so certain Fund Two bills that would normally go to the fund must be allocated to the management company instead.
    3. **Deal/borrower level** — requires deal team confirmation every time; approximately **50% revision rate** after deal team review. Borrower sensitivity (e.g., financial hardship) often overrides the initial recommendation.
  - For deal-level bills where the borrower is responsible: Maycomb pays the legal vendor and waits for reimbursement (invoice to borrower or withheld from a disbursement). **Maycomb does not pay the vendor until reimbursement is received.** Tracking this reimbursement — and nudging when it hasn't arrived — is the most friction-heavy ongoing piece.
  - Approval routing: fund and management company bills → Ariella or Miljana (after Ariella departs). Deal-level → deal team, and typically Andy if unclear.
  - Danielle recommended a voice memo to flesh out the allocation rules more explicitly, as a precursor to any automation or flow chart.

### P-002 — Manual Quarterly Borrower Invoicing (Processes)
- **Area:** Processes.
- **Problem:** Danielle manually creates and sends invoices to borrowers each quarter for interest and principal payments. Not yet breaking at current volume, but expected to as the portfolio grows.
- **Current Thinking:** Treated as low priority since it's "not at the scale that it is really breaking things" yet.
- **Reframe:** This is a templated, calculation-driven task (amounts are derivable from loan terms) that is cheap to automate now, before volume growth makes it urgent — an easy, low-risk win.
- **Approach:** Identify or build a recurring invoice generation tool tied to loan/payment schedule data. Status: SOP delivered by Danielle. Workflow deep-dive completed (June 23–24).
- **Key findings from workflow deep-dive:**
  - Approximately **15 active borrowers** currently receive quarterly invoices (some legacy borrowers do not have quarterly invoices yet — Maycomb is standardizing this).
  - Invoice amounts are pulled from the **Excel loan servicing model** (accrued interest tab, per-borrower tab).
  - Process: pull number from model → copy prior quarter's invoice → update dates, amount → send. Contact info typically stays the same.
  - **Deal team check happens before invoices are drafted** — confirms any fee adjustments, skipped quarters, or deal-specific quirks. This is the high-touch piece.
  - Total time once deal team confirms: approximately **1 hour** for all 15 invoices.
  - Danielle described the most time-consuming part as going into the loan servicing model to pull and verify the correct number.

### P-003 — Cross-Entity AP Run and Cash Allocation (Systems / Processes)
- **Area:** Systems / Processes.
- **Problem:** The biweekly AP run must allocate bills correctly across four LP funds, a single-member LLC, and the two-member management company, while also ensuring revenue earned by each fund/LLC is paid up to the management company (at least quarterly) so the management company can pay bills. This requires deep institutional knowledge of the corporate structure, even though the underlying payments are mostly fixed or easily calculable.
- **Current Thinking:** Because it requires "intimate knowledge of how the business works," it's assumed to need a skilled human running point each cycle.
- **Reframe:** The complexity is structural, not judgment-heavy — once the entity/allocation rules are documented, the mapping from bill → entity → payment source is mechanical and can be automated or semi-automated, even if a human still approves the run.
- **Approach:** Document the entity/allocation rules as an explicit rule set (in partnership with LeverPoint), then evaluate automating the allocation step ahead of the existing AP run. Status: SOP delivered by Danielle. Workflow deep-dive completed (June 23–24).
- **Key findings from workflow deep-dive:**
  - AP runs are **bi-weekly**. Typical volume: **10–20 invoices per run**.
  - Every invoice hits Danielle's inbox first — she sanity-checks it, logs it in her own tracker, and forwards it to LeverPoint. LeverPoint also tracks everything and sets up payments on the bank account (Maycomb has no direct bank access).
  - Every two weeks, LeverPoint sends back a reconciliation list; Danielle compares against her own tracker, resolves discrepancies, and finalizes the list. **Current double-tracking system was identified on the call as likely redundant work.**
  - Danielle's review of the finalized list and allocations: approximately **10 minutes**.
  - Biggest bottleneck: **management approval** (Ariella/Miljana) — described as a constant nudging process; this is what extends a 3-day process to potentially a week.
  - After approval, Danielle instructs LeverPoint to release payments (a few hours). Then payment portal approval — another round of nudging, as Danielle has no authority to approve payments herself.
  - Total elapsed time, start to payments released: **approximately 3 days** when smooth; **up to a week** when approvals lag.
  - **Quick win identified (no AI required):** A shared mailbox for invoices would eliminate the double-tracking step, create a single source of truth, and ease the transition to Varenka. JC recommended this; Barry confirmed he can implement it. Danielle also flagged this as critical for the vendor transition (some vendors only have her email).
  - Expense category allocation: LeverPoint applies Maycomb's expense categories (set annually via a detailed budget submission). For regular/known vendors they categorize well; new vendors require Danielle to flag the category. A rules-based auto-categorization from invoice/vendor data was identified as a potential future automation.
  - AP run SOP notes this process is connected to the legal bill tracking process — legal bills feed into the AP run once the allocation/reimbursement situation is resolved.

### P-004 — Budget-to-Actuals Review and Variance Reporting (Processes / Systems)
- **Area:** Processes / Systems.
- **Problem:** The fund administrator sends a monthly budget-to-actuals report, but it's "not accurate enough really to use" as-is. Maycomb instead does a manual quarterly deep review where Ariella works through variances by hand to decide whether to adjust the budget, which line items matter, and why — described as relying on her judgment ("amazing mind") rather than a defined process.
- **Current Thinking:** Variance review is assumed to require expert manual interpretation each quarter because line items vary in importance and the fund admin's draft isn't trustworthy.
- **Reframe:** Most of this can be reduced to explicit threshold rules (e.g., flag variances >50% and >$10,000) plus a model that drafts a recommendation off historical variance patterns — leaving the human only to approve or override a generated suggestion, rather than build the analysis from scratch.
- **Approach:** Build a rules-based variance flagging report against the fund admin's monthly actuals, then layer an LLM-generated narrative/recommendation on flagged items for human sign-off, aiming to compress the quarterly review into a short approval meeting. Status: Not started.

### P-005 — No AI/Automation Roadmap Behind the New Claude Rollout (People / Processes)
- **Area:** People / Processes.
- **Problem:** Maycomb just opened enterprise Claude access to staff with usage guidelines but no strategic plan for how different functions should actually use it, and no process to capture and standardize what individual employees discover works.
- **Current Thinking:** Rollout is treated as step one ("opening the sandbox"); the assumption is that letting people experiment freely is sufficient for now.
- **Reframe:** Without a standardization loop, usage will fragment — some staff will become heavy "early adopters" building ad hoc solutions, others will barely use the tool, and inconsistent practice becomes harder to unwind the longer it runs. A lightweight surfacing-and-standardizing process needs to exist alongside the freedom to experiment.
- **Approach:** Design a simple internal process for surfacing effective individual AI usage patterns and promoting them to team standard practice; pair with the do's/don'ts guidance already drafted. Status: Not started.

### P-006 — Institutional Knowledge Walking Out the Door (People)
- **Area:** People.
- **Problem:** Ariella (COO/CFO) and Danielle (Analyst) — the two people who hold the most detailed knowledge of the back/middle-office processes above — are both exiting within weeks of each other (June 30 and July 10 last days), before a Director of Finance & Ops or Analyst replacement is hired.
- **Current Thinking:** Treated as an unplanned, "deeply concerning" coincidence to be managed with an interim fractional COO bridging the gap.
- **Reframe:** The departures, while risky, create a forcing function: process documentation has to happen now regardless of automation plans, and that documentation work is the same work this engagement needs anyway — the transition and the diagnostic/automation engagement can directly reinforce each other if SOP capture happens immediately.
- **Approach:** Prioritize capturing or co-developing SOPs for the processes in P-001 through P-004 before June 30 (Danielle's last full-time day), using any SOPs already drafted internally as a starting point. Status: **Three SOPs delivered** (Legal Bill Tracking, AP Run, Quarterly Borrower Invoicing). Workflow deep-dive completed June 23–24. Budget-to-actuals SOP still to be created — Danielle noted this is less urgent (happens twice a year) and is more of an Ariella conversation. Danielle used Claude's transcript-to-SOP tool for two of the three SOPs — a direct use case example she found highly effective.

---

## 8. Action Plan

**Plan Overview:** Six problems are in the register, clustering almost entirely around back-office financial operations (P-001 through P-004) plus two structural/organizational issues (P-005, P-006) that affect how any solution gets adopted and how fast institutional knowledge needs to be captured. The hardest constraint is time: Danielle's full-time departure on June 29 is the effective deadline for capturing process knowledge before it becomes much more expensive to reconstruct. Ariella's stated top priority — turning budget-to-actuals review into something closer to a one-meeting approval — depends on first having clean allocation rules and SOPs in place (P-003 and P-006), so documentation has to come before any tooling. The sequencing logic below puts knowledge capture first, quick automatable wins next, and the more structurally complex AP/budget work last, once rules are documented and the fund administrator is looped in.

### People

**Problems in scope:** P-005, P-006

**Workstream: SOP Capture Before Transition**
- **Approach:** Treat Danielle and Ariella's departures as a forcing function — fast-track documentation of every process they currently run manually.
- **What it involves:** Request and review any SOPs already drafted internally; run structured interviews/working sessions with Danielle (before June 29) and Ariella (before July 10) to document legal bill tracking, invoicing, AP run logic, and budget-to-actuals review step by step.
- **Key Result:** Written SOPs exist for all four back-office processes (P-001 through P-004) before Danielle's last full-time day.
- **Timeline:** 1–2 weeks, starting immediately; hard deadline of June 29.

**Workstream: AI Usage Standardization Process**
- **Approach:** Build a lightweight loop for surfacing effective Claude usage patterns and promoting the best ones to team-wide standard practice.
- **What it involves:** Light interviews with the 12-person team on current Claude usage; define a simple "find it, flag it, standardize it" review cadence; align with the existing do's/don'ts guidelines.
- **Key Result:** A documented standardization process is in place and one usage pattern has been promoted to team standard.
- **Timeline:** 2–3 weeks, can run concurrent with SOP capture.

### Processes

**Problems in scope:** P-001, P-002

**Workstream: Legal Bill Tracker Rebuild**
- **Approach:** Replace the manual Excel-based legal bill log with a structured workflow encoding the fund/borrower allocation and payment-reimbursement rules.
- **What it involves:** Map the full bill lifecycle from the SOP capture workstream; define allocation rules; build/select a replacement tracking tool.
- **Key Result:** Legal bills are logged, allocated, and tracked through payment without manual cross-referencing conversations.
- **Timeline:** 3–4 weeks, starts after SOP capture for this process is done.

**Workstream: Automated Borrower Invoicing**
- **Approach:** Replace manual quarterly invoice creation with a templated, schedule-driven generation tool.
- **What it involves:** Pull loan/payment schedule data; build a recurring invoice template and generation trigger; validate against current borrower invoices.
- **Key Result:** Quarterly borrower invoices are generated automatically pending one human review/send step.
- **Timeline:** 2 weeks, can run concurrent with the legal bill tracker workstream.

### Systems

**Problems in scope:** P-003, P-004

**Workstream: Cross-Entity AP Allocation Rules**
- **Approach:** Document the bill-to-entity and revenue-to-management-company allocation logic as an explicit rule set, in coordination with the fund administrator.
- **What it involves:** Formalize the allocation rules from the SOP capture workstream; coordinate with the fund admin on data handoff; pilot automated/semi-automated allocation on the next biweekly AP run.
- **Key Result:** AP run allocation follows a documented rule set rather than relying on one person's institutional knowledge.
- **Timeline:** 4 weeks, starts after SOP capture and requires fund admin coordination.

**Workstream: Budget Variance Flagging and Recommendation Engine**
- **Approach:** Build a rules-based variance report against the fund admin's monthly actuals, then layer an LLM-generated recommendation for flagged items.
- **What it involves:** Define threshold rules (e.g., >50% and >$10,000 variance); build the flagging report off the fund admin's monthly data feed; prototype an LLM-generated narrative/recommendation step for human approval.
- **Key Result:** Quarterly budget-to-actuals review is reduced to a short approval meeting on a pre-flagged, pre-drafted report.
- **Timeline:** 4–5 weeks, starts after the AP allocation rules workstream (shares the same underlying entity/fund-admin data).

### Recommended Sequence

1. SOP Capture Before Transition (People) — must finish, or be substantially underway, before June 29.
2. AI Usage Standardization Process (People) — concurrent with #1.
3. Legal Bill Tracker Rebuild (Processes) — starts once SOP capture for that process is complete.
4. Automated Borrower Invoicing (Processes) — concurrent with #3.
5. Cross-Entity AP Allocation Rules (Systems) — starts once SOP capture is complete and fund admin coordination begins.
6. Budget Variance Flagging and Recommendation Engine (Systems) — starts after #5, since it depends on the same allocation/entity data.

---

## 9. Engagement Metrics

- **Comprehension:** Ungraded — baseline. Maycomb leadership clearly understands the problem space and articulated specific automatable rules unprompted (e.g., variance thresholds); comprehension appears high going in.
- **Adherence:** Ungraded — baseline.
- **Adoption:** Ungraded — baseline. Watch-point: Claude enterprise rollout is brand new with no usage standard yet, so early adoption signal is not yet measurable.
- **Velocity:** Ungraded — baseline. Watch-point: the June 29 / July 10 departure timeline creates real time pressure that could push velocity expectations beyond what the engagement can support if SOP capture slips.
- **Volume:** Ungraded — baseline. Six problems identified in a single discovery call; volume is moderate-to-high for a free, exploratory engagement and may need prioritization if scope expands.

---

## 10. Recommended Service Tier

Six diagnosed problems, two of which (P-003 AP allocation, P-004 budget variance) require coordination with an external fund administrator and carry real organizational risk (departing staff, no current backup), suggest this engagement should move from the initial free/in-kind diagnostic scope into a structured paid engagement once the SOP capture and quick-win automations (P-001, P-002) are delivered. Given the concurrency required across People, Processes, and Systems workstreams, and the hard deadline created by Danielle's June 29 departure, an ongoing retainer-style engagement (rather than a one-off project) is appropriate to maintain coordination with the fund administrator and the incoming Director of Finance & Ops once hired.

> No pricing tier discussion needed yet — engagement remains in the free/in-kind diagnostic phase; revisit once scope expands beyond the initial discovery work.

---

## Open Questions for Maycomb

1. Ariella's phone and mobile *(email confirmed: arotenberg@maycombcapital.com)*. Also: capture her personal/forwarding contact before July 10 to retain the relationship. Ariella was out the week of June 23–24 — follow up on return.
2. Danielle's phone and mobile *(email confirmed: dschweitzer@maycombcapital.com)*.
3. Barry Porozni's exact title, company name, and contact details *(confirmed: outside IT vendor, not internal staff; scope includes SharePoint, shared mailbox infrastructure, and Claude Enterprise admin controls)*.
4. Confirm Maycomb Capital's legal entity name(s) / any trade name, plus headquarters address and main phone.
5. LeverPoint primary contact name, and whether they should be looped into the engagement directly *(fund administrator name confirmed: LeverPoint, also referred to as Ultimis)*.
6. Status/timeline for hiring the interim fractional COO, Director of Finance & Ops, and Analyst — should the engagement plan to onboard them once in place? *(Analyst hire targeted by August per Danielle; other timelines unknown.)*
7. ~~Existing SOPs already drafted internally~~ — **RESOLVED: Three SOPs delivered (Legal Bill Tracking, AP Run, Quarterly Borrower Invoicing). Budget-to-actuals SOP to follow — Ariella conversation.**
8. ~~Any additional systems in use~~ — **RESOLVED: Full stack confirmed — Affinity (CRM), Slack, Teams (video only), SharePoint, ShareFile, DocuSign, Adobe, Expensify, LeverPoint, internal Excel loan servicing model.**
9. MSA confidentiality clause — *confirmed, MSA sent. MSA not yet signed as of June 23–24 — Ariella was out. Follow up on return.*
10. Pricing tiers/rate structure — *not needed yet; revisit if scope expands beyond the free engagement.*
11. Confirm with Barry: who holds the Claude Enterprise admin seat and what controls are currently configured (global toggle, group restrictions). Recommendation to disable Cowork and Claude Code by default was affirmed on the call.
