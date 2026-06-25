---
title: Maycomb Capital — Current State Workflow Map
date: 2026-06-24
tags:
  - client
  - project
ai: claude
status: needs-attention
---

# Current State Workflow Map — Maycomb Capital

**Blue Tusk | AI & Automation Advisory | Phase One Discovery Artifact**

> **Purpose.** Maps the *current* (as-is) state of Maycomb Capital's four back-office finance workflows so each can be rendered as a single **left-to-right linear flow** on the canvas. Each workflow below is one horizontal spine of **core steps**, sequenced left → right. Under each core step are its **sub-steps / details** — what goes in, what comes out, who owns it, where it happens — which become the cards that hang off that step on the canvas.
>
> **Structure for the canvas.** Read the numbered core steps as the horizontal spine (Core Step 1 → 2 → 3 …). Each core step's bullet list is the detail stack for that node. A later **"Overall" workflow** will string these four spines together where they connect (legal bills feed the AP run; AP allocations feed budget-to-actuals; invoicing revenue feeds the same financial picture).
>
> **Color/type tagging is intentionally omitted** — colors come from implementation tracking later, not from this map.
>
> **Source basis.** The four Maycomb-authored SOPs ([[Maycomb_Capital_Legal_Bills_SOP]], [[Maycomb_Capital_AP_Run_SOP]], [[Maycomb_Capital_Quarterly_Invoicing_SOP]], [[Maycomb_Capital_Budgeting_SOP]]) and the 2026-06 workflow deep-dive call (Danielle Schweitzer + Barry Porozni + John-Carlos). Anywhere the source doesn't pin down a step, field, owner, or hand-off, it's marked **`[TO CONFIRM]`** — these double as the next-pass interview checklist (primary conduit: Danielle through her part-time period; Varenka as she assumes the AP run; Ariella/Andi for approval-layer questions before July 10).
>
> **As-is, including dysfunction.** Breakpoints (manual gaps, redundancies, failure modes) are marked **⚠** where they exist today. Fixes are not designed here — the reframes and automation approaches live in the discovery brief's Problem Register (P-001 through P-004).
>
> **Note on source precedence.** Where the SOPs and the transcript diverge, the divergence is itself flagged — the SOPs are the more recently formalized, deliberate account (written April–June 2025/2026), while the transcript captures live nuance and pain points Danielle voiced that the SOPs smooth over. Both are recorded.

---

## Legend

- **Core Step** — a node on the horizontal spine.
- **→** — sequence / hand-off to the next step.
- **In / Out** — data, document, or trigger consumed / produced by a step.
- **Owner** — role responsible.
- **System** — where it happens.
- **`[TO CONFIRM]`** — not specified in source, or SOP/transcript conflict; verify next pass.
- **⚠** — known breakpoint / friction / redundancy in the current state.

---

# Workflow Index

| #   | Workflow                          | Spine (core steps, left → right)                                                                 | Final Deliverable                          |
| --- | --------------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------ |
| 1   | Legal Bills Tracking & Allocation | Receive → Store → Log → Determine Responsibility/Allocation → Approve → Reimbursement Gate → Pay via AP → Quarterly Review | Legal bill paid, allocated, reconciled     |
| 2   | AP Run (Biweekly)                 | Receive & Forward → Log Internally → Receive AP List → Verify → MD Approval → Confirm to Admin → Verify in Bank & Notify → Dual Release | Vendor payments released, allocated        |
| 3   | Quarterly Borrower Invoicing      | Build Borrower List → Draft Invoices → Deal-Team Review → Send to Borrowers → Track Payments     | Borrowers invoiced, payments reconciled    |
| 4   | Annual Budget & Budget-to-Actuals | Build Budget → Monthly Monitor → Mid-Year Right-Size → Year-End Right-Size                       | Approved budget, kept accurate all year    |

---

# Cross-Workflow Foundations — Entities, Admin & Approval Layer

**Source: all four SOPs + transcript.** Three things sit underneath all four workflows and are mapped once here rather than repeated on every spine, because the canvas would otherwise show duplicate logic. Several core steps below cross-reference this section.

### The entity structure (why allocation exists at all)
Maycomb runs a **Management Company** (two-member LLC, the operating business) over **four LP fund vehicles** plus **one single-member LLC**. The Management Company pays essentially all bills; costs and revenue are generated mostly by the funds and the single-member LLC. This is why every bill and invoice has to be *allocated* — assigned to the entity that truly bears the cost — and why funds periodically settle up to the Management Company via **"Due From" / "Due to Manager"** balances. This allocation logic is the connective tissue between Workflows 1, 2, and 4.

### Ultimus Leverpoint (fund administrator) — the external engine
- **Role across workflows:** Collects forwarded invoices, prepares the AP list and allocations spreadsheet, sets up ACH/wire payments in the Wells Fargo portal, and releases payments once approved (W2). Produces the monthly financial statements including the budget-to-actuals page (W4). Tracks actual spend all year.
- **Critical control fact:** Ultimus sets up payments; **Maycomb does not have transactional bank access** — only View Only in Wells Fargo. Payment *release* requires two Maycomb management approvers in the portal. This split is deliberate cash control.
- **Naming note:** Referred to as "Ultimus Leverpoint," "Ultimis," and "Leverpoint" interchangeably across the SOPs and transcript. Treated as one entity here. `[TO CONFIRM: exact legal name and the primary day-to-day contact.]`
- **⚠** Ultimus "are not machines" (Danielle) — they miss or mis-record forwarded invoices often enough that Maycomb maintains an independent tracker specifically to catch it (see W2 Step 2 / Step 4).

### The approval layer (who signs off on what) — `[TO CONFIRM]` reconciliation needed
The SOPs and transcript name approvers differently across processes. Recorded here because every workflow funnels into one of these sign-offs:

| Decision | SOP-named approver | Transcript-named approver | Status |
| --- | --- | --- | --- |
| AP run list & allocations (W2) | Miljana (MD/Partner) — "previously Ariella" | Ariella, → Miljana after Ariella departs | Consistent: Ariella was the holder; Miljana inherits. |
| Discretionary Fund legal allocations (W1) | Andi | Andy "if it's unclear"; deal team otherwise | `[TO CONFIRM: "Andi" (budget/legal SOP) vs "Andy" (transcript) — same person? And is Andi/Andy distinct from Ariella and Miljana?]` |
| Annual budget & revisions (W4) | Andi (Managing Partner) | Not discussed (Ariella out for this call) | `[TO CONFIRM: confirm Andi owns budget approval; reconcile with COO collaboration role.]` |
| Each Wells Fargo payment release (W2) | Any two management team members | Danielle has no release authority; "constant nudging" | Consistent. |

**⚠ Transition risk across all four:** Ariella (COO/CFO, July 10 last day) and Danielle (Analyst, June 30 last full-time day) both exit within weeks. Varenka (office manager) inherits the AP run; the incoming Analyst (targeted onboarded by August) and Director of Finance & Ops inherit the rest. Every approval and institutional-knowledge dependency below is a transition exposure point.

---

# Workflow 1 — Legal Bills Tracking & Allocation

**Spine:** `Receive → Store → Log → Determine Responsibility/Allocation → Approve → Reimbursement Gate → Pay via AP → Quarterly Review`

**Trigger:** External counsel (e.g., Manatt, Morgan Lewis) sends a legal bill to Maycomb.
**Final deliverable:** Legal bill paid by the Management Company via the AP run, allocated to the correct entity, reimbursement collected where a Borrower or Fund is responsible, and reconciled quarterly.
**Frequency:** Bills arrive ~weekly; allocation determination done monthly; allocation reconciliation done quarterly.

> **Key relationship:** This workflow does not pay anything itself — it determines *who owes* and *whether reimbursement must be collected first*, then hands the bill to Workflow 2 (AP Run) for actual payment. Legal bills are initially fronted by the Management Company via the AP run regardless of who ultimately bears the cost.

### Core Step 1 — Invoice Receipt
- **In:** Legal bill from external counsel.
- **Out:** Bill in the hands of the Operations Team.
- **Owner/System:** Operations Team / Email (Outlook).
- **⚠** Bills sometimes go directly to the Deal Team instead of Operations — these must be manually forwarded to Operations, and there's no guarantee they always are. A bill that never reaches Operations never gets logged.

### Core Step 2 — Storage
- **In:** Received legal bill.
- **Out:** Bill saved into the law-firm-specific Legal Bill folder.
- **Owner/System:** Operations Team / SharePoint (Legal Bill folder, organized by law firm).

### Core Step 3 — Invoice Tracking
- **In:** Stored bill; bill details.
- **Out:** Row in the Legal Bills Tracker — invoice number, date, amount, allocation, payment status, description.
- **Owner/System:** Operations Team / Legal Bills Tracker (Excel on SharePoint).

### Core Step 4 — Responsibility & Allocation Determination
- **In:** All legal invoices accumulated over the month; knowledge of what each bill relates to.
- **Out:** For each bill, a determination of (a) which entity has **responsibility** for the cost and (b) which entity the cost is **allocated** to, sorted into one of three scenarios (below).
- **Owner/System:** Operations Team, in coordination with Deal Teams / Excel (Legal Bills Tracker). Done **monthly**.
- **The three scenarios:**
  - **A — Management Company Responsibility & Allocation.** Legal work relates to Management Company activities (internal policies, HR). Paid by Mgmt Co via AP run; no further allocation. *(Transcript: immediately determinable by Danielle, ~0% revision rate.)*
  - **B — Fund Responsibility & Allocation.** Legal work relates to Fund-level matters (subscription docs, side letters). Paid by Mgmt Co via AP run; marked **due from Fund**. *(Transcript exception: Fund II has hit a legal-cost cap in a specific bucket, so some Fund II bills that would normally allocate to the fund are instead absorbed by the Management Company.)*
  - **C — Deal-level Responsibility, Fund Allocation.** Legal work relates to a specific deal within the legal-cost limit (loan agreement/amendment). Borrower is typically responsible. → routes through the **Reimbursement Gate** (Core Step 6). *(Transcript: ~50% of deal-level determinations come back revised after deal-team review, driven by borrower-specific context.)*
- **⚠** Scenario C requires per-bill deal-team input every time; this is the judgment-heavy, slowest, most error-prone branch. Scenarios A and B are effectively rules-based.
- **⚠ Knowledge dependency:** Danielle's "gut" for which scenario applies is exactly the institutional knowledge leaving at end of June. Successor (Varenka / new Analyst) will not have it. *(Transcript: Danielle to record a voice memo articulating the allocation rules explicitly.)*

### Core Step 5 — Approval
- **In:** Operations Team's proposed responsibility/allocation.
- **Out:** Approved allocation, cleared to proceed to payment instructions.
- **Owner/System:** Operations Team (self-approves straightforward cases) → Andi (for discretionary Fund-charged bills) / Email or Slack `[TO CONFIRM: channel for Andi's monthly Partnership Expenses review]`.
- **Approval routing:** Straightforward → Operations Team approval is sufficient. Discretionary (e.g., a modified loan template charged to a Fund) → Operations sends Andi a **monthly list** of Partnership Expenses legal allocations for review.
- **⚠ `[TO CONFIRM]`** SOP says discretionary Fund bills go to **Andi**; transcript says deal-level bills go to the **deal team**, and "Andy" only when unclear. Reconcile the two routings — they may be describing different cut-points (Fund-level discretionary vs deal-level).

### Core Step 6 — Reimbursement Gate (Scenario C only)
- **In:** Approved deal-level bill where the Borrower (or a Fund) is responsible.
- **Out:** Cash to cover the bill confirmed in the Fund account, via one of two methods.
- **Owner/System:** Operations Team / `[TO CONFIRM: tracking mechanism — Legal Bills Tracker columns, reminders]`.
- **Two reimbursement methods:**
  - Deduct the legal bill amount from a loan disbursement to the Borrower, **or**
  - Invoice the Borrower directly (payment directed to the Fund account).
- **⚠ Hard gate (confirmed in both sources):** The Management Company will **NOT** pay the legal vendor until the covering cash is actually in the Fund account. This is the single most friction-heavy ongoing piece — Danielle must set manual reminders and chase whether the borrower invoice has been paid / the deduction has cleared before the bill can move to the AP run.
- **⚠** No automated follow-up exists; reimbursement chasing is fully manual and interrupt-driven.

### Core Step 7 — Pay via AP Run
- **In:** Approved bill (Scenarios A/B), or reimbursed bill (Scenario C after the gate clears).
- **Out:** Bill included in the next biweekly AP run; paid by the Management Company.
- **Owner/System:** Operations Team / hand-off into **Workflow 2** (see W2 Step 1). Marked **due from Fund** where applicable.

### Core Step 8 — Payment & Status Update + Quarterly Reconciliation
- **In:** Completed payment; the period's legal invoices.
- **Out:** (1) Legal Bills Tracker updated (payment + allocation columns). (2) Quarterly review of all included legal invoices for correct allocation, completed **before** Due-to-Manager balances are paid.
- **Owner/System:** Operations Team / Excel (Legal Bills Tracker). Quarterly cadence.
- **Notes:** The quarterly review is the control that catches mis-allocations before inter-entity balances settle — it ties directly into the Fund-to-Management-Company "Due From" settlement.

---

# Workflow 2 — AP Run (Biweekly)

**Spine:** `Receive & Forward → Log Internally → Receive AP List → Verify → MD Approval → Confirm to Admin → Verify in Bank & Notify → Dual Release`

**Trigger:** Vendor invoices arrive (rolling) and the biweekly cycle reaches its Friday close.
**Final deliverable:** All verified, approved vendor payments released from Wells Fargo and correctly allocated across entities/expense categories.
**Frequency:** Biweekly — typically the 1st and 3rd Fridays of each month. End-to-end ~3 days when smooth, up to a week when approvals lag (transcript). Volume: ~10–20 invoices per run (transcript).
**Owner:** Finance & Ops Associate (Danielle or Varenka — either runs a given cycle).

### Core Step 1 — Receive & Forward Invoices to Ultimus
- **In:** Vendor invoices (PDF/other) by email — from vendors, conference organizers, other counterparties. Includes legal bills handed off from **W1 Step 7**.
- **Out:** Each invoice forwarded to Ultimus Leverpoint by email, as received (rolling, not batched).
- **Owner/System:** Finance & Ops Associate / Email (Outlook).
- **Notes:** Forward immediately on receipt — don't wait for cycle end — and log in the internal tracker at the same time (Step 2).
- **⚠ (transcript)** Every invoice hits Danielle's inbox first as a manual sanity-check, then is forwarded one-by-one. Ultimus receives nothing directly from vendors. This makes Danielle (soon Varenka) a single human router for all AP intake.

### Core Step 2 — Log Invoices in Internal Tracker
- **In:** Invoice details: vendor, date, amount, expense category.
- **Out:** Updated internal Excel invoice tracker (all invoices for the two-week cycle).
- **Owner/System:** Finance & Ops Associate / Microsoft Excel on SharePoint.
- **Notes:** The tracker is an **independent second record**, kept specifically to catch invoices Ultimus misses or mis-records.
- **⚠ Redundancy flagged on the call:** Maycomb tracks every invoice *and* Ultimus tracks every invoice, purely so the two lists can be reconciled later (Step 4). JC flagged this as likely-removable duplicate work — a shared mailbox could make a single forwarded stream the master record, collapsing the dual-tracking. Danielle agreed; the dual-track persists today mostly because "it was what happened before." (See Cross-Workflow Observations.)

### Core Step 3 — Receive AP List & Supporting Docs from Ultimus
- **In:** Notification from Ultimus that the biweekly AP list is ready.
- **Out:** Three items pulled from a Sharefile folder: (1) **AP List** (Excel), (2) folder of all individual **invoice PDFs**, (3) **Allocations Spreadsheet** (Excel).
- **Owner/System:** Finance & Ops Associate / Email + Sharefile. End of each two-week cycle (1st/3rd Friday).

### Core Step 4 — Review & Verify (AP List, PDFs, Allocations)
- **In:** Ultimus AP List, PDF folder, Allocations Spreadsheet (Sharefile) + internal tracker (SharePoint).
- **Out:** Verified AP List and Allocations; a list of discrepancies/corrections emailed to Ultimus; re-reviewed updated files.
- **Owner/System:** Finance & Ops Associate / Excel + PDF viewer + Sharefile. *(Transcript: ~10 minutes of actual review time once lists are in hand.)*
- **Three checks:** (1) Cross-check Ultimus AP List against the internal tracker — every invoice on both. (2) Open each PDF, confirm amount matches the AP List. (3) Review Allocations — correct expense category (Legal, Rent, etc.) and correct fund/entity; cross-fund items appear as **"Due From."**
- **Out (loop):** Corrections → Ultimus by email → Ultimus updates Sharefile → re-review until clean. Unresolvable discrepancy → escalate to MD.
- **⚠** This entire step exists to catch Ultimus errors; it's the back-half of the dual-tracking redundancy. The correction loop can iterate multiple times.

### Core Step 5 — MD Approval of AP List & Allocations
- **In:** Finalized AP List + Allocations, confirmed accurate.
- **Out:** MD/Partner sign-off requested and granted.
- **Owner/System:** Finance & Ops Associate sends → Miljana (MD/Partner) approves / Slack. *(Previously Ariella.)*
- **⚠ Biggest bottleneck (transcript):** Management approval is "a constant nudging process" — it slips on busy approvers' priority lists and is what stretches a 3-day run toward a week. Danielle has no authority to move past it; she can only chase.

### Core Step 6 — Confirm Approval to Ultimus & Await Payment Setup
- **In:** MD Slack approval.
- **Out:** Email to Ultimus confirming approval; Ultimus sets up ACH/wire payments in Wells Fargo and confirms when ready.
- **Owner/System:** Finance & Ops Associate / Email (Outlook) → Ultimus → Wells Fargo.
- **Notes:** Do **not** confirm to Ultimus without explicit written MD approval.

### Core Step 7 — Verify Payments in Wells Fargo & Notify Management
- **In:** Ultimus confirmation that payments are set up; approved AP List.
- **Out:** (1) Verified that every Wells Fargo payment matches the approved AP List (vendor + amount, line by line). (2) Slack to the full management team: # and $ of ACH payments, # and $ of wires, any unusual items, AP List attached.
- **Owner/System:** Finance & Ops Associate / Wells Fargo Online Portal (View Only, individual credentials) + Slack. *(Transcript: ~10 minutes.)*

### Core Step 8 — Dual Management Approval & Release Confirmation
- **In:** Slack message from Step 7 with AP List.
- **Out:** (1) Each payment approved by **two** management team members in Wells Fargo. (2) Slack confirmation from approvers. (3) Finance & Ops Associate confirms all released, then emails Ultimus to confirm.
- **Owner/System:** Any two management members (portal credentials) + Finance & Ops Associate / Wells Fargo + Slack + Email.
- **Notes:** Two-approver release is a hard financial control. Cycle completes here; next cycle begins the following 1st/3rd Friday.
- **⚠ (transcript)** This is a *second* nudging round — Danielle has no release authority and must chase two managers to approve in-portal before vendors are actually paid.

### Exception handling (from SOP)
- Tracker-vs-AP-List mismatch → flag to Ultimus, don't proceed to Step 5 until resolved.
- Wrong amount/allocation → email Ultimus, re-review updated files.
- MD unavailable → escalate to another MD/Partner; never proceed without written approval.
- Unusual/unexpected invoice → flag in the Step 7 Slack; if legitimacy is uncertain, raise with MD before including.

---

# Workflow 3 — Quarterly Borrower Invoicing

**Spine:** `Build Borrower List → Draft Invoices → Deal-Team Review → Send to Borrowers → Track Payments`

**Trigger:** Quarter approaches; invoices go out ~30 days before quarter-end (the payment due date — Mar 1, Jun 1, Sep 1, Dec 1 for Mar 31 / Jun 30 / Sep 30 / Dec 31 due dates).
**Final deliverable:** Each owing borrower invoiced for interest (plus any principal/fees), with incoming payments tracked in the loan servicing model.
**Frequency:** Quarterly. ~15 active borrowers invoiced (transcript). ~1 hour to draft all invoices once amounts are known (transcript); the time sink is pulling/verifying figures from the loan servicing model.
**Owner:** Finance & Ops Associate.

### Core Step 1 — Build Borrower List & Confirm with Deal Teams
- **In:** Full active-borrower list across all funds; known prior-quarter exceptions (capitalizations, waivers).
- **Out:** Confirmed list of who will / won't be invoiced this quarter, with reasons noted for exclusions.
- **Owner/System:** Finance & Ops Associate / Loan servicing model (Excel, SharePoint) for the list + Slack for deal-team confirmation. Done **midway through the quarter**.
- **Notes:** Most borrowers get an invoice. Exceptions = capitalized interest (interest added to loan balance, no cash due, no invoice), waived payments, or other special arrangements. **Deal teams have final authority** — no borrower is excluded without written Slack confirmation.
- **⚠** Some legacy borrowers don't yet have quarterly invoices; Maycomb is standardizing onto a quarterly cadence (transcript). `[TO CONFIRM: how many legacy borrowers remain off-cycle.]`

### Core Step 2 — Draft Invoices for Each Borrower
- **In:** Confirmed borrower list; loan servicing model (interest calcs); fund-specific invoice templates; borrower contact info (from deal-closing docs).
- **Out:** A completed draft invoice per borrower, saved as `[Fund Name] Invoice – [Borrower Name]`.
- **Owner/System:** Finance & Ops Associate / Excel + fund invoice templates (SharePoint).
- **Per-invoice procedure:** Open correct fund template → fill borrower contact details → reference loan servicing model for interest due → add any principal/fee amounts (from the model or confirmed with deal team case-by-case) → save under naming convention → double-check amounts.
- **⚠ Time sink (transcript):** The bottleneck is going into the loan servicing model, verifying the per-borrower accrued-interest figure is accurate, and pulling it. Repeat borrowers are faster — copy the prior quarter's invoice, update dates/amount. Highly templated and the clearest automation candidate of the four workflows.
- **`[TO CONFIRM]`** Whether principal/fee amounts are reliably in the loan servicing model or routinely require deal-team confirmation (SOP says "may be either").

### Core Step 3 — Send Draft Invoices to Deal Teams for Review
- **In:** All draft invoices.
- **Out:** Deal-team confirmation (via Slack) that details are correct, or a correction list.
- **Owner/System:** Finance & Ops Associate sends → Deal Teams review / Slack.
- **Verify list:** borrower contact info, interest amount, principal/fee amounts, anything else on the invoice.
- **Notes:** No invoice goes to a borrower until **all** deal teams confirm in writing. Corrections → update in SharePoint → re-confirm.
- **Notes (transcript):** The deal-team check is the high-touch part and happens **before** drafts are finalized/sent — it absorbs deal-specific quirks (fee adjustments, skipped quarters). Sequencing confirmed: deal-team checks precede send.

### Core Step 4 — Send Finalized Invoices to Borrowers
- **In:** Confirmed invoices; borrower contact emails.
- **Out:** Invoices emailed to each borrower, ~30 days before quarter-end.
- **Owner/System:** Finance & Ops Associate / Email (Outlook).
- **Notes:** Send to the correct contact; if multiple contacts, confirm with deal team. Retain sent-email records; log the send date per borrower for dispute protection.

### Core Step 5 — Track Incoming Payments & Update Loan Servicing Model
- **In:** Sent invoices (amounts due); incoming payment notifications in Wells Fargo.
- **Out:** Loan servicing model updated for all payments received; early payments noted with actual receipt date.
- **Owner/System:** Finance & Ops Associate / Wells Fargo (View Only) + loan servicing model (Excel, SharePoint).
- **Notes:** Mark payment received on the official due date (standard practice); if paid early, add a cell note ("Paid early — received [date]"). Most reconciliation happens the week after quarter-end. Payment not in by due date → flag to deal team via Slack.
- **⚠** Monitoring is manual portal-watching against a mental/spreadsheet model; no automated match of incoming payment → expected invoice.

### Exception handling (from SOP)
- Capitalized/waived interest → never exclude without written deal-team confirmation; note reason on the list.
- Principal/fee not in model → confirm figure with deal team before drafting.
- Missing borrower contact → request from deal team before sending.
- Payment not received by due date → flag to deal team; don't act without their guidance.
- Borrower disputes amount → route to deal team; Finance & Ops doesn't negotiate terms.

---

# Workflow 4 — Annual Budget & Budget-to-Actuals

**Spine:** `Build Budget → Monthly Monitor → Mid-Year Right-Size → Year-End Right-Size`

**Trigger:** Calendar — annual build in January; monitoring every month; formal right-sizing in June and December.
**Final deliverable:** An approved annual budget that is kept accurate all year through monthly monitoring and two formal revisions, feeding accurate year-end projections (critical for tax estimates).
**Frequency:** Annual build + monthly monitoring + two right-sizing reviews.
**Owner:** Finance & Ops Associate (builds); COO (collaborates); Andi/Managing Partner (approves); Ultimus (tracks actuals, produces statements).

> **Transcript priority note:** Danielle deprioritized this workflow for the engagement — it runs twice a year, Ultimus does much of the underlying work, and it's "more of an Ariella conversation." The SOP (more complete than the transcript on this process) is the primary source for the map below; the budget-to-actuals *automation* opportunity (P-004) is owned by Ariella, not Danielle.

### Core Step 1 — Build the Annual Budget (January)
- **In:** Prior-year actuals (Ultimus's final year-end financials); knowledge of upcoming-year activities (planned hires, AGM, retreat, software changes, contractor/vendor pricing changes).
- **Out:** Completed annual budget Excel, approved and sent to Ultimus. Saved as `FY[Year] Budget Maycomb Outcomes`.
- **Owner/System:** Finance & Ops Associate + COO build together; Andi approves (Slack); Associate sends (Email) / Excel (SharePoint).
- **Notes:** One line per significant expense category (comp, legal, rent, software, events, contractors). Start from prior-year actuals, adjust for known changes. No send to Ultimus until Andi confirms in Slack.

### Core Step 2 — Monthly Monitoring of Budget-to-Actuals (Ongoing)
- **In:** Monthly financial statements from Ultimus (include a budget-to-actuals comparison page).
- **Out:** Internal notes on significant variances; ad-hoc budget update to Ultimus if a major unplanned expense lands outside the June/December cycles.
- **Owner/System:** Finance & Ops Associate (primary); COO (consulted on significant variances) / Excel + Email. Save each statement as `[Month] [Year] MOutcomes FS`.
- **Notes:** Review the full budget-to-actuals page monthly; focus on large categories (comp, legal) and anything tracking well above/below budget.
- **⚠ (transcript)** Ariella's quarterly/periodic deep review currently relies on her judgment ("amazing mind") rather than a defined variance-flagging rule set. The SOP formalizes monthly monitoring but not the threshold logic Ariella applies — the reframe (flag variances >50% and >$10K, then auto-draft a recommendation) is the P-004 opportunity and depends on Ariella, who was absent for this call.

### Core Step 3 — Mid-Year Right-Sizing (June)
- **In:** YTD monthly financials (Jan–May/Jun); current annual budget; updated expectations for the rest of the year.
- **Out:** Revised remainder-of-year budget, approved and sent to Ultimus. Saved versioned (`...v2` or dated).
- **Owner/System:** Finance & Ops Associate + COO; Andi approves (Slack); Associate sends (Email) / Excel.
- **Per-category review:** Is actual above/below budget? Is the variance one-time or ongoing? Any known upcoming costs not in the original budget? Revise remaining months accordingly.

### Core Step 4 — Year-End Right-Sizing (December)
- **In:** YTD monthly financials (Jan–Nov); most recent budget; remaining year-end expenses.
- **Out:** Final revised budget projecting accurate year-end financials, approved and sent to Ultimus.
- **Owner/System:** Finance & Ops Associate + COO; Andi approves (Slack); Associate sends (Email) / Excel.
- **⚠ Time-sensitive:** Maycomb needs a close-to-final year-end view in December to calculate and pay **quarterly tax estimates before Dec 31**. Must finish early enough in December for Andi's approval + Ultimus's incorporation. Year-close actuals then become the next January build's baseline (loops to Step 1).

### Exception handling (from SOP)
- Major unplanned mid-year expense → assess with COO whether an ad-hoc Ultimus update is needed now vs. waiting.
- Monthly financials late/missing → follow up with Ultimus by email; never skip the monthly review.
- Unexplained large variance → discuss with COO before flagging to Ultimus (could be timing, miscategorization, or real overspend).
- Andi unavailable → escalate to another partner, especially in December.

---

# Overall Workflow (Placeholder — to be strung together)

Once each spine is on the canvas, the **Overall** flow links them where they actually connect. The real seams (not `[TO CONFIRM]` — these are confirmed in the SOPs):

`W1 Legal Bills → W2 AP Run` — **confirmed, the strongest seam.** Legal bills are fronted by the Management Company via the AP run (W1 Step 7 → W2 Step 1). Scenario-C bills wait at the W1 Reimbursement Gate until covering cash lands, *then* enter the AP run.

`W2 AP Run → W4 Budget-to-Actuals` — **confirmed.** AP allocations are the actual expense data Ultimus uses to build the monthly budget-to-actuals page (W2 Step 4 allocations → W4 Step 2 monitoring). Correct allocation in W2 is what makes W4's variance review meaningful.

`W3 Borrower Invoicing → W4 Financial Picture` — **confirmed (looser).** Borrower interest/principal is the revenue side; payment tracking (W3 Step 5) feeds the broader financial picture W4 monitors. Less tightly coupled than the expense-side seams.

`W1 Quarterly Reconciliation ↔ Fund "Due From" settlement` — the W1 Step 8 quarterly allocation review runs **before** Due-to-Manager balances are paid, tying legal-bill allocation accuracy to the inter-entity cash settlement that also underlies W2 allocations.

> Build note: the Overall spine is **not** a fifth workflow — it's the join of the four spines at these seams, with the **entity/allocation structure** (see Cross-Workflow Foundations) as the shared backbone all four touch. The AP Run is the central hub: W1 feeds into it, and it feeds W4.

---

# Cross-Workflow Observations — Structural Context

These are not workflow steps. They're structural and organizational dynamics — confirmed via the 2026-06 deep-dive call and the SOPs — that materially affect how the four workflows execute. They explain several breakpoints flagged above but are not themselves automatable process; they're context the AI & automation plan must account for.

1. **The dual-tracking redundancy (AP Run).** Maycomb keeps a full internal invoice tracker *and* Ultimus keeps its own list, solely so the two can be reconciled (W2 Steps 2 + 4). This evolved historically — Danielle's predecessor (Ariella) didn't track on Maycomb's side, inconsistencies appeared, so Danielle added a parallel tracker. JC flagged on the call that a **shared mailbox** (a single forwarded invoice stream becoming the master record) could collapse the duplication and ease the Varenka transition. This is a confirmed, low-cost, no-AI quick win — but it does require consciously changing the process rather than continuing "what happened before." Barry can implement the shared mailbox. The dual-track persists today only because it's how it was always done.

2. **No transactional bank access by design.** Maycomb has View Only in Wells Fargo; Ultimus sets up payments and Maycomb's two-approver release is the only Maycomb-side action on the money. This is deliberate cash control and is *not* a target for removal — but it does mean the AP run's slowest segments (approval nudging, two-approver release) are structural, and any automation can only speed the *coordination* around them, not the controls themselves.

3. **Approver-name reconciliation needed.** The SOPs name **Andi** (legal discretionary allocations; all budget approvals) and **Miljana** (AP run, "previously Ariella"). The transcript names **Ariella → Miljana** for AP and **"Andy"** for unclear legal calls. Whether Andi/Andy is one person distinct from Ariella and Miljana, and exactly which decisions each owns post-transition, needs confirming before any approval-routing automation is designed. `[TO CONFIRM]`

4. **Institutional knowledge concentration + transition.** The judgment in W1 Step 4 (which allocation scenario), the W3 loan-servicing-model figure verification, and the W4 variance interpretation all currently live in two departing heads (Danielle end of June; Ariella July 10). The SOPs were authored specifically to externalize this — two of the three operational SOPs were generated using Claude's transcript-to-SOP tool, a working AI use case Danielle found highly effective. SOP capture is the bridge; Varenka (AP run) and the incoming Analyst/Director of Finance & Ops inherit the rest.

5. **Net effect on the automation plan.** The four workflows are unusually well-documented for a 12-person firm (the SOPs are detailed and recent), which lowers automation risk. The highest-leverage moves surfaced here map directly to the discovery brief's Problem Register: the shared-mailbox/dual-track collapse (P-003), templated invoice generation (P-002), legal-bill allocation rules + reimbursement-gate tracking (P-001), and budget variance-flagging (P-004, Ariella-owned). None of the structural controls (two-approver release, no bank access, deal-team final authority) should be automated away — they're the firm's financial guardrails.

---

# `[TO CONFIRM]` Checklist — Next Discovery Pass

Grouped for an efficient interview (Danielle through her part-time period; Varenka as she assumes the AP run; Ariella/Andi for the approval layer before July 10).

**Approval layer (cross-workflow)**
- Reconcile Andi (SOPs) vs "Andy" (transcript) vs Ariella vs Miljana — who is who, and which decisions each owns after the transition.
- Channel for Andi's monthly Partnership Expenses legal-allocation review (email vs Slack).
- Confirm the W1 discretionary-Fund routing (Andi) vs the transcript's deal-level routing (deal team) — are these different cut-points or a genuine conflict?

**Legal Bills (W1)**
- Tracking mechanism for the Reimbursement Gate (which Legal Bills Tracker columns; how reminders are set).
- The exact legal-cost limit/cap logic per fund (Fund II cap referenced in transcript) — where it's documented and who maintains it.

**AP Run (W2)**
- Ultimus Leverpoint's exact legal name and primary day-to-day contact.
- Whether the shared-mailbox change is adopted (and if so, whether the internal tracker is retired or kept as backup).

**Quarterly Invoicing (W3)**
- How many legacy borrowers remain off the quarterly cadence.
- Whether principal/fee amounts are reliably in the loan servicing model or routinely need deal-team confirmation.

**Budget (W4)**
- Confirm Andi owns budget approval; reconcile with the COO collaboration role and Ariella's historical ownership.
- The variance-threshold logic Ariella applies in her deep review (needed for P-004) — capture before July 10.

**Loan servicing software (future, cross-workflow)**
- Status of the paused loan-servicing-software evaluation (borrower portal + auto-invoicing) — confirmed ~1 year out; revisit timing.

---

*End of current-state map. Next artifact: visual linear flow per workflow on the canvas, then the Overall flow joining the four spines at the confirmed seams (W1→W2→W4; W3→financial picture), with the entity/allocation structure as the shared backbone.*
