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

> **Purpose.** Maps the *current* (as-is) state of Maycomb Capital's four back-office finance workflows so each can be rendered as a single **left-to-right linear flow** on the canvas. Each workflow below is one horizontal spine of **core steps**, sequenced left → right. Each core step carries the SOP's full field set — **Inputs**, **Where inputs come from**, **Software & tools**, **Who is responsible**, **Outputs**, **Where outputs go**, and **Notes** — so the cards that hang off each node on the canvas are fully specified.
>
> **Source basis.** This map is a direct translation of the four Maycomb-authored SOPs ([[Maycomb_Capital_Legal_Bills_SOP]], [[Maycomb_Capital_AP_Run_SOP]], [[Maycomb_Capital_Quarterly_Invoicing_SOP]], [[Maycomb_Capital_Budgeting_SOP]] — full copies in the `SOPs/` subfolder), with live nuance and pain points from the 2026-06 workflow deep-dive call (Danielle Schweitzer + Barry Porozni + John-Carlos) layered on as annotations.
>
> **Placeholders (added July 7, 2026).** Workflows 5–8 are revenue/value-driver-side processes surfaced on the July 7, 2026 value-drivers call with Ariella Rotenberg and Martina Madrid Sebring. They have no SOP source yet, so they appear only as brief placeholder stubs pointing back to [[20260616_discovery-brief-maycomb-capital]] Section 11 — not full spines like Workflows 1–4.
>
> **Annotation layers on top of the SOP content:**
> - **⚠** — a known breakpoint / friction / redundancy in the current state (mostly surfaced on the call; the SOPs describe the process as intended, the ⚠ notes describe where it strains in practice).
> - **`[TO CONFIRM]`** — not specified in source, or a place where the SOP and transcript diverge; verify next pass. These double as the interview checklist at the foot of the document.
> - ***(Transcript)*** — a detail Danielle gave verbally that the SOP doesn't capture (volumes, timings, revision rates).
>
> **Color/type tagging is intentionally omitted** — colors come from implementation tracking later, not from this map.

---

## Legend

- **Core Step** — a node on the horizontal spine.
- **→** — sequence / hand-off to the next step.
- **Inputs / Where inputs come from / Software & tools / Who is responsible / Outputs / Where outputs go / Notes** — the SOP field set carried on every core step.
- **`[TO CONFIRM]`** — not specified in source, or SOP/transcript conflict; verify next pass.
- **⚠** — known breakpoint / friction / redundancy in the current state.

---

# Workflow Index

| #   | Workflow                          | Spine (core steps, left → right)                                                                 | Final Deliverable                          |
| --- | --------------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------ |
| 1   | Legal Bills Tracking & Allocation | Legal Work → Receipt & Storage → Tracking → Responsibility/Allocation → Approval → Payment Instructions (3 scenarios) → Payment & Status Update | Legal bill paid, allocated, reconciled     |
| 2   | AP Run (Biweekly)                 | Receive & Forward → Log Internally → Receive AP List → Verify → MD Approval → Confirm to Admin → Verify in Bank & Notify → Dual Release | Vendor payments released, allocated        |
| 3   | Quarterly Borrower Invoicing      | Build Borrower List → Draft Invoices → Deal-Team Review → Send to Borrowers → Track Payments     | Borrowers invoiced, payments reconciled    |
| 4   | Annual Budget & Budget-to-Actuals | Build Budget → Monthly Monitor → Mid-Year Right-Size → Year-End Right-Size                       | Approved budget, kept accurate all year    |
| 5   | Deal Sourcing & Capital Deployment *(placeholder)* | Not yet mapped | TBD |
| 6   | Investor Relations & Capital Raising *(placeholder)* | Not yet mapped | TBD |
| 7   | Borrower Asset Management / Portfolio Support *(placeholder)* | Not yet mapped | TBD |
| 8   | Outcome Data Collection & Annual Impact Reporting *(placeholder — see P-007)* | Not yet mapped | TBD |

> Workflows 5–8 are revenue/value-driver-side processes identified July 7, 2026 (see [[20260616_discovery-brief-maycomb-capital]] Section 11). Unlike Workflows 1–4, they are not yet built from SOPs — placeholders only, to be scoped once source material (deal-team interviews, Martina's input, or the incoming Investor Relations hire starting August 3) is available.

---

# Cross-Workflow Foundations — Entities, Systems & Approval Layer

Mapped once here rather than repeated on every spine. Several core steps below cross-reference this section.

### The entity structure (why allocation exists at all)
Maycomb runs a **Management Company** (two-member LLC, the operating business) over **four LP fund vehicles** plus **one single-member LLC**. The Management Company pays essentially all bills; costs and revenue are generated mostly by the funds and the single-member LLC. Every bill and invoice therefore has to be **allocated** — assigned to the entity that truly bears the cost — and funds periodically settle up to the Management Company via **"Due From" / "Due to Manager"** balances. This allocation logic is the connective tissue between Workflows 1, 2, and 4.

### Systems & tools used across the four workflows (from the SOPs)
| Tool | Role |
| --- | --- |
| **Email (Outlook)** | Receiving vendor/legal invoices; forwarding invoices to Ultimus; sending budget updates and approvals; sending finalized borrower invoices. |
| **SharePoint (Maycomb Capital)** | Central storage: internal invoice tracker, Legal Bills Tracker, loan servicing model, invoice templates, borrower lists, budget files, monthly financial statements. |
| **Microsoft Excel** | Internal invoice tracker; Legal Bills Tracker; AP List & Allocations review; loan servicing model; invoice templates; annual budget. |
| **Sharefile (Ultimus Leverpoint)** | Secure portal where Ultimus uploads the AP List (Excel), PDF invoices, and Allocations Spreadsheet for review. |
| **Wells Fargo Online Portal (View Only)** | Verifying that payments set up by Ultimus match the approved AP List; monitoring incoming borrower payments; the two-approver payment-release control. Individual credentials. |
| **Slack** | Deal-team confirmations (invoicing); MD approval of AP runs; management-team AP notifications; Andi's budget approvals. |

### Ultimus Leverpoint (fund administrator) — the external engine
- **Role across workflows:** Collects forwarded invoices, prepares the AP List and Allocations Spreadsheet, sets up ACH/wire payments in Wells Fargo, and releases payments once approved (W2). Produces the monthly financial statements including the budget-to-actuals page (W4). Tracks actual spend all year. **Does not build the budget — that is internal (W4).**
- **Critical control fact:** Ultimus sets up payments; **Maycomb has View Only bank access only.** Payment *release* requires two Maycomb management approvers in the Wells Fargo portal. Deliberate cash control.
- **Naming note:** "Ultimus Leverpoint," "Ultimis," and "Leverpoint" are used interchangeably across the SOPs and transcript. Treated as one entity here. `[TO CONFIRM: exact legal name and the primary day-to-day contact.]`
- **⚠ *(Transcript)*** Ultimus "are not machines" — they miss or mis-record forwarded invoices often enough that Maycomb keeps an independent tracker specifically to catch it (W2 Steps 2 + 4).

### The approval layer (who signs off on what) — `[TO CONFIRM]` reconciliation needed
| Decision | SOP-named approver | Transcript-named approver | Status |
| --- | --- | --- | --- |
| AP run list & allocations (W2) | Miljana (MD/Partner) — "previously Ariella" | Ariella, → Miljana after Ariella departs | Consistent: Ariella was the holder; Miljana inherits. |
| Discretionary Fund legal allocations (W1) | Andi | Andy "if it's unclear"; deal team otherwise | `[TO CONFIRM: "Andi" vs "Andy" — same person? Distinct from Ariella/Miljana?]` |
| Annual budget & revisions (W4) | Andi (Managing Partner) | Not discussed (Ariella out for this call) | `[TO CONFIRM: confirm Andi owns budget approval; reconcile with COO collaboration role.]` |
| Each Wells Fargo payment release (W2) | Any two management team members | Danielle has no release authority; "constant nudging" | Consistent. |

**⚠ Transition risk across all four:** Ariella (COO/CFO, July 10 last day) and Danielle (Analyst, June 30 last full-time day) both exit within weeks. Varenka (office manager) inherits the AP run; the incoming Analyst (targeted onboarded by August) and Director of Finance & Ops inherit the rest.

---

# Workflow 1 — Legal Bills Tracking & Allocation

**Source SOP:** [[Maycomb_Capital_Legal_Bills_SOP]] (April 2026)
**Spine:** `Legal Work Performed → Invoice Receipt & Storage → Invoice Tracking → Responsibility & Allocation Determination → Approval → Payment Instructions (one of 3 scenarios) → Payment & Status Update`

**Purpose (from SOP):** A standardized process for tracking, allocating, and paying legal bills across the firm.
**Key relationship:** Legal bills are initially paid by the Management Company through the **biweekly AP run (Workflow 2)**. This workflow defines *when and how* those costs are allocated and reimbursed to the Management Company — it determines who owes and whether reimbursement must be collected first, then hands the bill to W2 for actual payment.
**Frequency:** Bills arrive *(Transcript: ~weekly)*; responsibility/allocation determined **monthly**; allocation reconciled **quarterly**.

### Core Step 1 — Legal Work Performed
- **Inputs:** A legal matter requiring external counsel.
- **Where inputs come from:** Management Company, Fund, or Deal/Borrower activity that triggers legal work.
- **Software & tools:** None (external counsel activity).
- **Who is responsible:** External counsel (e.g., Manatt, Morgan Lewis).
- **Outputs:** Completed legal work; a legal bill to follow.
- **Where outputs go:** Billed to Maycomb (Core Step 2).
- **Notes:** Legal services are performed by external counsel.

### Core Step 2 — Invoice Receipt & Storage
- **Inputs:** Legal bill from external counsel.
- **Where inputs come from:** Lawyers (e.g., Manatt, Morgan Lewis) send bills to Maycomb. Sometimes sent directly to the Deal Team.
- **Software & tools:** Email (Outlook); SharePoint (Legal Bill folder, organized by law firm).
- **Who is responsible:** Operations Team. (Deal Team forwards to Operations if a bill lands with them first.)
- **Outputs:** Legal bill saved into the law-firm-specific Legal Bill folder.
- **Where outputs go:** SharePoint Legal Bill folder (specified per law firm).
- **Notes:** If legal bills are sent directly to the Deal Team, they should be forwarded to the Operations Team.
- **⚠** A bill that goes to the Deal Team and is never forwarded never gets logged — manual hand-off with no guaranteed catch.

### Core Step 3 — Invoice Tracking
- **Inputs:** Stored legal bill and its details.
- **Where inputs come from:** The saved bill (Core Step 2).
- **Software & tools:** Legal Bills Tracker (Excel on SharePoint).
- **Who is responsible:** Operations Team.
- **Outputs:** A tracker row capturing invoice number, date, amount, allocation, payment status, description, etc.
- **Where outputs go:** Legal Bills Tracker (Excel on SharePoint).
- **Notes:** Operations Team inputs legal bill details into the Legal Bills Tracker excel.

### Core Step 4 — Responsibility & Allocation Determination
- **Inputs:** All legal invoices accumulated over the month; knowledge of what each bill relates to.
- **Where inputs come from:** Legal Bills Tracker (accumulated bills); Deal Teams (coordination on responsibility).
- **Software & tools:** Microsoft Excel (Legal Bills Tracker).
- **Who is responsible:** Operations Team, in coordination with Deal Teams. Done **monthly**.
- **Outputs:** For each bill, a determination of (a) which entity has **responsibility** for the cost and (b) which entity the cost is **allocated** to — sorted into one of three scenarios (see Core Step 6).
- **Where outputs go:** Recorded in the Legal Bills Tracker; passed to Approval (Core Step 5).
- **Notes:** On a monthly basis the Operations Team gathers all legal invoices accumulated in that time and determines responsibility and allocation for each.
- **⚠ *(Transcript)*** Scenario A (Management Co) and B (Fund) are effectively rules-based and immediately determinable (~0% revision rate). Scenario C (Deal-level) requires per-bill deal-team input and ~50% of those determinations come back revised after deal-team review, driven by borrower-specific context.
- **⚠ Knowledge dependency:** Danielle's "gut" for which scenario applies is institutional knowledge leaving at end of June. *(Transcript: Danielle to record a voice memo articulating the allocation rules explicitly for her successor.)*

### Core Step 5 — Approval
- **Inputs:** The Operations Team's proposed responsibility/allocation.
- **Where inputs come from:** Core Step 4.
- **Software & tools:** Email or Slack `[TO CONFIRM: channel for Andi's monthly Partnership Expenses review]`.
- **Who is responsible:** Operations Team (self-approves straightforward cases); Andi (reviews discretionary Fund-charged bills).
- **Outputs:** Approved responsibility/allocation, cleared to proceed to payment instructions.
- **Where outputs go:** Payment Instructions (Core Step 6).
- **Notes (from SOP):** If the decision is straightforward, Operations Team approval is sufficient. If a bill is being charged to a Fund and the decision is more discretionary (e.g., a modified loan template), the Operations Team sends a **monthly list** of Partnership Expenses legal-bill allocations to Andi for review.
- **⚠ `[TO CONFIRM]`** SOP routes discretionary Fund bills to **Andi**; transcript routes deal-level bills to the **deal team**, with "Andy" only when unclear. Reconcile — these may be different cut-points (Fund-level discretionary vs deal-level).

### Core Step 6 — Payment Instructions (one of three scenarios)
After approval, the relevant payment instructions are followed for each bill. There are three primary scenarios:

**Scenario A — Management Company Responsibility & Allocation**
- **Use when:** Legal work relates to Management Company activities (e.g., internal policies, HR matters).
- **Payment instructions:** Paid by the Management Company via AP run; no further allocation required.
- **Note:** If the Management Company elects to cover a bill that would otherwise belong to a Fund or Borrower, document this decision in the Legal Bills Tracker.

**Scenario B — Fund Responsibility & Allocation**
- **Use when:** Legal work relates to Fund-level matters (e.g., subscription documents, side letters).
- **Payment instructions:** Paid by the Management Company via AP run; marked **due from Fund**.
- **Note:** If a Fund agrees to cover Borrower-related legal costs (e.g., Borrower exceeds legal limit), document this in the Legal Bills Tracker.
- **⚠ *(Transcript)*** Fund II has hit a legal-cost cap in a specific bucket, so some Fund II bills that would normally allocate to the fund are instead absorbed by the Management Company.

**Scenario C — Deal-level Responsibility, Fund Allocation**
- **Use when:** Legal work relates to a deal and the bill is within the legal-cost limit where applicable (e.g., loan agreement/amendment).
- **Payment instructions:** Either (a) deduct the legal bill amount from a loan disbursement, **or** (b) invoice the Borrower (payment directed to the Fund). After reimbursement is confirmed via either method: the Management Company pays the invoice via the AP run; marked **due from Fund**.
- **⚠ Hard gate (SOP, emphasized):** The legal bill will **NOT** be paid by the Management Company until the cash to cover it is in the Fund account — whether from a deduction off a loan advance or from a Borrower invoice payment.
- **⚠ *(Transcript)*** This reimbursement-then-pay sequence is the single most friction-heavy ongoing piece: Danielle sets manual reminders and chases whether the borrower invoice has been paid / the deduction has cleared before the bill can enter the AP run. No automated follow-up exists. `[TO CONFIRM: exact tracking mechanism — which Legal Bills Tracker columns, how reminders are set.]`
- **Hand-off:** All three scenarios route the bill into **Workflow 2 (AP Run)** for actual payment (W2 Step 1).

### Core Step 7 — Payment & Status Update + Quarterly Reconciliation
- **Inputs:** Completed payment confirmation; the period's legal invoices.
- **Where inputs come from:** AP run (W2) payment completion; Legal Bills Tracker.
- **Software & tools:** Microsoft Excel (Legal Bills Tracker).
- **Who is responsible:** Operations Team.
- **Outputs:** (1) Legal Bills Tracker updated (payment + allocation columns). (2) Quarterly review of all included legal invoices for correct allocation.
- **Where outputs go:** Legal Bills Tracker; feeds the Fund "Due to Manager" settlement.
- **Notes:** Once payment is complete, update the tracker. On a **quarterly** basis, **before** the Due-to-Manager balances are paid, all included legal invoices are reviewed by the Operations Team to ensure proper allocation.

---

# Workflow 2 — AP Run (Biweekly)

**Source SOP:** [[Maycomb_Capital_AP_Run_SOP]] (June 2025)
**Spine:** `Receive & Forward → Log Internally → Receive AP List → Verify → MD Approval → Confirm to Admin → Verify in Bank & Notify → Dual Release`

**Purpose (from SOP):** End-to-end biweekly process for collecting, verifying, allocating, approving, and paying vendor invoices, with appropriate financial controls.
**Frequency:** Biweekly — typically the 1st and 3rd Fridays of each month. *(Transcript: end-to-end ~3 days when smooth, up to a week when approvals lag; ~10–20 invoices per run.)*
**Document Owner:** Finance & Operations Associate (Danielle / successor). Either Danielle or Varenka runs a given cycle.
**Reviewed By:** Managing Director / Partner (Miljana).

### Core Step 1 — Receive & Forward Invoices to Ultimus Leverpoint
- **Inputs:** Vendor invoices (PDF or other formats) received via email. *(Includes legal bills handed off from W1.)*
- **Where inputs come from:** Email to Danielle and/or Varenka directly from vendors, conference organizers, or other external parties.
- **Software & tools:** Email (Outlook).
- **Who is responsible:** Finance & Operations Associate (Danielle or Varenka).
- **Outputs:** Each invoice forwarded to Ultimus Leverpoint via email; internal tracker updated with invoice details.
- **Where outputs go:** Ultimus Leverpoint (by email); internal Excel tracker on SharePoint.
- **Notes:** Forward invoices to Ultimus as soon as they are received — do not wait until the end of the cycle. Log the invoice in the internal Excel tracker at the same time (Step 2).
- **⚠ *(Transcript)*** Every invoice hits Danielle's inbox first as a manual sanity-check, then is forwarded one-by-one; Ultimus receives nothing directly from vendors. This makes the Associate a single human router for all AP intake.

### Core Step 2 — Log Invoices in the Internal Tracker
- **Inputs:** Invoice details — vendor name, invoice date, invoice amount, expense category.
- **Where inputs come from:** From each invoice email received; logged at the same time as forwarding to Ultimus (Step 1).
- **Software & tools:** Microsoft Excel (stored on Maycomb Capital SharePoint).
- **Who is responsible:** Finance & Operations Associate (Danielle or Varenka).
- **Outputs:** Updated internal Excel invoice tracker with all invoices received during the two-week cycle.
- **Where outputs go:** Saved to Maycomb Capital SharePoint. Used in Step 4 to cross-check Ultimus's AP list.
- **Notes:** The tracker serves as an independent second record. It is critical for catching any invoices that Ultimus may have missed or recorded incorrectly.
- **⚠ Redundancy flagged on the call:** Maycomb tracks every invoice *and* Ultimus tracks every invoice, purely so the two can be reconciled in Step 4. JC flagged this as likely-removable duplicate work — a shared mailbox could make a single forwarded stream the master record. The dual-track persists mostly because "it was what happened before." (See Cross-Workflow Observations.)

### Core Step 3 — Receive AP List & Supporting Documents from Ultimus
- **Inputs:** Notification from Ultimus that the biweekly AP list is ready for review.
- **Where inputs come from:** Ultimus sends a Sharefile link via email at the end of each two-week cycle (typically the 1st or 3rd Friday). The folder contains: (1) AP List (Excel), (2) a folder of all individual invoice PDFs, (3) the Allocations Spreadsheet (Excel).
- **Software & tools:** Email (Outlook); Sharefile.
- **Who is responsible:** Finance & Operations Associate (Danielle or Varenka) — receives and opens documents.
- **Outputs:** Three documents downloaded/accessed from Sharefile: AP List (Excel), PDF invoice folder, Allocations Spreadsheet (Excel).
- **Where outputs go:** Reviewed locally; used in Step 4 for verification.

### Core Step 4 — Review & Verify the AP List, PDFs, and Allocations
- **Inputs:** (1) Ultimus AP List (Excel), (2) PDF invoice folder, (3) Allocations Spreadsheet (Excel) — all from Sharefile. (4) Internal invoice tracker from SharePoint.
- **Where inputs come from:** Sharefile (Ultimus documents); Maycomb Capital SharePoint (internal tracker).
- **Software & tools:** Microsoft Excel (AP List and Allocations); PDF viewer (invoice PDFs); Sharefile.
- **Who is responsible:** Finance & Operations Associate (Danielle or Varenka). *(Transcript: ~10 minutes of review once lists are in hand.)*
- **Outputs:** Verified AP List and Allocations Spreadsheet; a list of discrepancies/correction requests sent to Ultimus via email.
- **Where outputs go:** Corrections communicated to Ultimus by email; Ultimus updates documents in Sharefile; re-review the updated version before Step 5.
- **Notes — three checks:** (1) Cross-check Ultimus AP List against the internal tracker — every invoice on both. (2) Open each PDF invoice and confirm the amount matches the AP List. (3) Review the Allocations Spreadsheet — correct expense category (e.g., Legal, Rent) and correct fund/entity; cross-fund items appear in a 'Due From' allocation. Repeat until accurate. If a discrepancy cannot be resolved, escalate to the Managing Director.
- **⚠** This step exists to catch Ultimus errors; it is the back-half of the dual-tracking redundancy and the correction loop can iterate multiple times.

### Core Step 5 — Send AP List & Allocations to MD for Final Approval
- **Inputs:** Finalized AP List (Excel) and Allocations Spreadsheet (Excel), confirmed accurate after Step 4.
- **Where inputs come from:** Sharefile (Ultimus's updated documents).
- **Software & tools:** Slack.
- **Who is responsible:** Finance & Operations Associate sends; Managing Director / Partner (Miljana) reviews and approves.
- **Outputs:** Slack to Miljana with the AP List and Allocations attached, requesting final sign-off.
- **Where outputs go:** Managing Director's Slack. Once Miljana approves, proceed to Step 6.
- **Notes:** The MD performs a final check that all invoices are present, amounts are correct, and allocations make sense. Proceed only once they confirm approval by Slack.
- **⚠ Biggest bottleneck *(Transcript)*:** Management approval is a "constant nudging process" — it slips on busy approvers' lists and is what stretches a 3-day run toward a week. The Associate has no authority to move past it; she can only chase.

### Core Step 6 — Confirm Approval to Ultimus & Await Payment Setup
- **Inputs:** Slack approval from the Managing Director (Step 5).
- **Where inputs come from:** Managing Director's Slack reply.
- **Software & tools:** Email (Outlook).
- **Who is responsible:** Finance & Operations Associate (Danielle or Varenka).
- **Outputs:** Email to Ultimus confirming the AP List and Allocations are approved and payments can be set up.
- **Where outputs go:** Sent to Ultimus by email. Ultimus then sets up ACH and wire payments in the Wells Fargo portal and emails back to confirm payments are ready for release.
- **Notes:** Do not send this confirmation until you have explicit written approval from the Managing Director. Once Ultimus confirms payments are ready, proceed to Step 7.

### Core Step 7 — Verify Payments in Wells Fargo & Notify Management Team
- **Inputs:** (1) Confirmation email from Ultimus that payments are set up in Wells Fargo. (2) Approved AP List (Excel) from Step 4/5.
- **Where inputs come from:** Ultimus confirmation email; Sharefile (AP List).
- **Software & tools:** Wells Fargo Online Portal (View Only — individual credentials); Slack.
- **Who is responsible:** Finance & Operations Associate (Danielle or Varenka). *(Transcript: ~10 minutes.)*
- **Outputs:** (1) Verified that all payments in Wells Fargo match the approved AP List (vendor + amount, line by line). (2) Slack message to the full management team summarizing the AP run with the AP List attached.
- **Where outputs go:** Slack message to the management team channel, AP List attached.
- **Notes:** Log into Wells Fargo with your own View Only credentials and compare each payment against the approved AP List. The Slack message should include: total number and dollar amount of ACH payments, total number and dollar amount of wire payments, any unusual items warranting awareness, and the full AP List attached.

### Core Step 8 — Management Approval in Wells Fargo & Payment Release Confirmation
- **Inputs:** Slack message from Step 7 with AP List attached.
- **Where inputs come from:** Slack (management team channel).
- **Software & tools:** Wells Fargo Online Portal (management members log in with their own credentials); Slack; Email (Outlook).
- **Who is responsible:** Two members of the management team (any two with portal access); Finance & Operations Associate confirms release.
- **Outputs:** (1) Each payment approved by two management team members in Wells Fargo. (2) Management team Slack confirmation. (3) Associate confirms all payments released.
- **Where outputs go:** Associate confirms payment release with Ultimus by email.
- **Notes:** Each individual payment requires approval from two separate management team members — a financial control requirement. Once both approvals are in place, payments are released. Log into Wells Fargo (View Only) to confirm all show as released, then email Ultimus to confirm. This completes the cycle; the next begins on the following 1st or 3rd Friday.
- **⚠ *(Transcript)*** A *second* nudging round — the Associate has no release authority and must chase two managers to approve in-portal before vendors are actually paid.

### File Naming & Storage (from SOP)
- AP List (from Ultimus): `MOutcomes AP List [Date]` — e.g., MOutcomes AP List June 6 2025.
- Allocations Spreadsheet (from Ultimus): `MOutcomes AP Allocation List [Date]`.
- Internal Invoice Tracker: stored on Maycomb Capital SharePoint, following existing folder structure.

### Exception Handling (from SOP)
- **Tracker vs AP List mismatch** → flag to Ultimus by email with specifics; do not proceed to Step 5 until resolved.
- **Incorrect amount or allocation** → email Ultimus; re-review updated Sharefile documents before sending to the MD.
- **MD unavailable** → escalate to another MD/Partner; never proceed without written approval.
- **Unusual/unexpected invoice** → flag in the Step 7 Slack; if legitimacy is uncertain, raise with the MD before including.

---

# Workflow 3 — Quarterly Borrower Invoicing

**Source SOP:** [[Maycomb_Capital_Quarterly_Invoicing_SOP]] (June 2025)
**Spine:** `Build Borrower List → Draft Invoices → Deal-Team Review → Send to Borrowers → Track Payments`

**Purpose (from SOP):** End-to-end process for preparing, issuing, and tracking quarterly interest invoices to borrowers.
**Frequency:** Quarterly — invoices sent ~30 days before quarter-end (due dates Mar 31 / Jun 30 / Sep 30 / Dec 31; sends ~Mar 1 / Jun 1 / Sep 1 / Dec 1). *(Transcript: ~15 active borrowers; ~1 hour to draft all once amounts are known.)*
**Document Owner:** Finance & Operations Associate. **Reviewed By:** Deal Teams; MD/Partner.

### Core Step 1 — Create Borrower List & Confirm with Deal Teams
- **Inputs:** Full list of active borrowers across all funds; knowledge of any known exceptions (interest capitalizations, waivers) from prior quarters.
- **Where inputs come from:** Loan servicing model on SharePoint (full borrower list); deal teams via Slack (exception guidance).
- **Software & tools:** Microsoft Excel (SharePoint); Slack.
- **Who is responsible:** Finance & Operations Associate. Done **midway through the quarter**.
- **Outputs:** A confirmed borrower list showing who will and won't receive an invoice this quarter, with reasons noted for exclusions.
- **Where outputs go:** Sent to deal teams via Slack for confirmation; saved to SharePoint; used in Step 2.
- **Notes:** Most borrowers need an invoice. Exceptions = capitalized interest (added to loan balance, no cash due, no invoice), waived payments, or other special arrangements. Deal teams have final authority — do not exclude a borrower without written Slack confirmation. Save the final version to SharePoint before proceeding.
- **⚠ *(Transcript)*** Some legacy borrowers aren't yet on the quarterly cadence; Maycomb is standardizing. `[TO CONFIRM: how many legacy borrowers remain off-cycle.]`

### Core Step 2 — Create Draft Invoices for Each Borrower
- **Inputs:** (1) Confirmed borrower list from Step 1. (2) Loan servicing model (interest calculations). (3) Fund-specific invoice templates. (4) Borrower contact information (from deal closing).
- **Where inputs come from:** All files on SharePoint. Borrower contact info should be on file from deal-closing documentation — if missing, request from the relevant deal team via Slack.
- **Software & tools:** Microsoft Excel (SharePoint); invoice templates (SharePoint).
- **Who is responsible:** Finance & Operations Associate.
- **Outputs:** A completed draft invoice per borrower, saved as `[Fund Name] Invoice – [Borrower Name]`.
- **Where outputs go:** Saved to SharePoint; sent to deal teams for review in Step 3.
- **Notes (per-invoice):** (1) Open the correct fund's invoice template. (2) Fill in borrower contact details (name, address, email). (3) Reference the loan servicing model to calculate interest due. (4) Add any principal repayment or fee amounts — these may be in the loan servicing model or may need deal-team confirmation case-by-case. (5) Save under the naming convention. Double-check all amounts before review.
- **⚠ Time sink *(Transcript)*:** The bottleneck is going into the loan servicing model, verifying the per-borrower accrued-interest figure, and pulling it. Repeat borrowers are faster — copy the prior quarter's invoice, update dates/amount. The clearest automation candidate of the four workflows.
- **`[TO CONFIRM]`** Whether principal/fee amounts are reliably in the loan servicing model or routinely require deal-team confirmation (SOP says "may be either").

### Core Step 3 — Send Draft Invoices to Deal Teams for Review
- **Inputs:** Completed draft invoices for all borrowers (Step 2).
- **Where inputs come from:** SharePoint (saved invoice files).
- **Software & tools:** Slack.
- **Who is responsible:** Finance & Operations Associate (sends drafts); Deal Teams (review and confirm).
- **Outputs:** Deal-team confirmation via Slack that all invoice details are correct — or a list of corrections.
- **Where outputs go:** Once all invoices are confirmed correct, proceed to Step 4. If corrections are needed, update in SharePoint and re-confirm before sending.
- **Notes:** Ask deal teams to verify borrower contact information, interest amount, any principal/fee amounts, and anything else on the invoice. Do not send to borrowers until all deal teams confirm in writing via Slack.
- **Notes *(Transcript)*:** The deal-team check is the high-touch part and happens **before** drafts are finalized/sent — it absorbs deal-specific quirks (fee adjustments, skipped quarters). Sequencing confirmed.

### Core Step 4 — Send Finalized Invoices to Borrowers
- **Inputs:** Confirmed, finalized invoices for all borrowers (Step 3); borrower contact email addresses.
- **Where inputs come from:** SharePoint (invoice files); borrower contact info from deal-closing documentation on file.
- **Software & tools:** Email (Outlook).
- **Who is responsible:** Finance & Operations Associate.
- **Outputs:** Invoices emailed to each borrower contact, ~30 days before the quarter-end payment due date.
- **Where outputs go:** Sent directly to borrower email contacts; retain sent-email records in Outlook.
- **Notes:** Send each invoice to the correct contact email. If a borrower has multiple contacts, confirm with the deal team who should receive it. Keep a record of the send date per borrower in case of payment disputes.

### Core Step 5 — Track Incoming Payments & Update Loan Servicing Model
- **Inputs:** Sent invoices (amounts due per borrower); incoming payment notifications in Wells Fargo.
- **Where inputs come from:** Wells Fargo Online Portal (View Only, individual credentials); loan servicing model on SharePoint.
- **Software & tools:** Wells Fargo Online Portal (View Only); Microsoft Excel (SharePoint — loan servicing model).
- **Who is responsible:** Finance & Operations Associate.
- **Outputs:** Loan servicing model updated to reflect all payments received, including early payments noted with the actual receipt date.
- **Where outputs go:** Updated loan servicing model saved to SharePoint. No external output required.
- **Notes:** Monitor Wells Fargo from the invoice send date. As payments come in: (1) mark the payment received on the official due date (standard practice); (2) if a borrower paid early, add a cell note ("Paid early — received [actual date]"). Most reconciliation happens the week after quarter-end. If a payment hasn't arrived by the due date, flag it to the relevant deal team via Slack.
- **⚠** Monitoring is manual portal-watching against the spreadsheet; no automated match of incoming payment → expected invoice.

### File Naming & Storage (from SOP)
- Completed borrower invoice: `[Fund Name] Invoice – [Borrower Name]` — e.g., Maycomb Fund I Invoice – Acme Holdings.
- Borrower list (quarterly): follow existing SharePoint folder structure; save a confirmed copy once deal teams sign off.

### Exception Handling (from SOP)
- **Capitalized/waived interest** → never exclude without written deal-team confirmation via Slack; note the reason on the borrower list.
- **Principal/fee not in loan servicing model** → confirm the figure with the deal team via Slack before creating the invoice.
- **Missing borrower contact info** → request correct details from the relevant deal team via Slack before sending.
- **Payment not received by due date** → flag to the deal team via Slack immediately; don't act without their guidance.
- **Borrower disputes an amount** → route to the deal team; Finance & Operations does not negotiate loan terms or amounts.

---

# Workflow 4 — Annual Budget & Budget-to-Actuals

**Source SOP:** [[Maycomb_Capital_Budgeting_SOP]] (June 2025)
**Spine:** `Build Budget (Jan) → Monthly Monitor (ongoing) → Mid-Year Right-Size (Jun) → Year-End Right-Size (Dec)`

**Purpose (from SOP):** Maycomb's annual budgeting process and how the budget is monitored and right-sized through the year.
**Cadence:** Annual budget built in January; mid-year review in June; year-end review in December; monthly monitoring throughout.
**Document Owner:** Finance & Operations Associate. **Key Collaborators:** COO; Managing Partner (Andi). **External:** Ultimus (tracks actuals, produces monthly statements; does not build the budget).

> **Transcript priority note:** Danielle deprioritized this workflow for the engagement — it runs twice a year, Ultimus does much of the underlying work, and it's "more of an Ariella conversation." The budget-to-actuals *automation* opportunity (discovery brief P-004) is Ariella-owned.
>
> **Update July 7, 2026:** The Budget-to-Actuals SOP has now been captured (`SOPs/Maycomb_Capital_Budgeting_SOP`) and is the source basis for this Workflow 4 spine above. W4 is no longer blocked on Ariella's availability for documentation; the remaining Ariella-dependent item is the *variance-threshold logic* for the P-004 automation (see checklist below).

### Core Step 1 — Build the Annual Budget (January)
- **Inputs:** (1) Prior-year actuals (Ultimus's final year-end financial statements). (2) Knowledge of upcoming-year activities: planned hires, events (AGM, team retreat), software changes, contractor updates, pricing changes for existing vendors.
- **Where inputs come from:** Prior-year financials on SharePoint (named `[Month] [Year] MOutcomes FS`); upcoming activities discussed between the Associate and the COO.
- **Software & tools:** Microsoft Excel (SharePoint); Slack (Andi's approval); Email (Outlook, to send to Ultimus).
- **Who is responsible:** Finance & Operations Associate and COO (build together); Managing Partner Andi (approves); Associate (sends to Ultimus).
- **Outputs:** Completed annual budget Excel file, approved by Andi and sent to Ultimus.
- **Where outputs go:** Saved to SharePoint as `FY[Year] Budget Maycomb Outcomes`; emailed to Ultimus.
- **Notes:** Include a line item for every significant expense category (compensation, legal, rent, software, events, contractors). Start from prior-year actuals, adjust for known changes. Do not send to Ultimus until Andi confirms approval in Slack.

### Core Step 2 — Review Monthly Financials & Monitor Budget-to-Actuals (Ongoing)
- **Inputs:** Monthly financial statements from Ultimus, which include a budget-to-actuals comparison page.
- **Where inputs come from:** Received by email from Ultimus as an attachment; save each file to SharePoint immediately on receipt.
- **Software & tools:** Microsoft Excel (SharePoint); Email (Outlook).
- **Who is responsible:** Finance & Operations Associate (primary reviewer); COO (consulted on significant variances).
- **Outputs:** Internal notes on significant variances; an ad-hoc budget update to Ultimus if a major unplanned expense occurs outside the June/December cycles.
- **Where outputs go:** Notes kept internally (on the saved statement file or tracked separately); any ad-hoc budget updates emailed to Ultimus.
- **Notes:** Save each statement as `[Month] [Year] MOutcomes FS`. Review the full budget-to-actuals page monthly; focus on larger categories (compensation, legal) and anything tracking significantly above/below budget. If a major unplanned expense arises mid-month, flag to the COO and consider an ad-hoc Ultimus update rather than waiting for June/December.
- **⚠ *(Transcript)*** Ariella's periodic deep review relies on her judgment ("amazing mind") rather than a defined variance-flagging rule set. The reframe (flag variances >50% and >$10K, then auto-draft a recommendation) is the P-004 opportunity and depends on Ariella.

### Core Step 3 — Mid-Year Budget Right-Sizing (June)
- **Inputs:** (1) YTD monthly financial statements (Jan–May/Jun). (2) Current annual budget (`FY[Year] Budget Maycomb Outcomes`). (3) Updated knowledge of expected activities for the rest of the year.
- **Where inputs come from:** Monthly financials on SharePoint; current budget on SharePoint; business-activity updates from the COO.
- **Software & tools:** Microsoft Excel (SharePoint); Slack (Andi's approval); Email (Outlook, to send to Ultimus).
- **Who is responsible:** Finance & Operations Associate and COO (build revision together); Andi (approves); Associate (sends to Ultimus).
- **Outputs:** Revised remainder-of-year budget, approved by Andi and sent to Ultimus.
- **Where outputs go:** Saved to SharePoint, versioned (e.g., `FY2025 Budget Maycomb Outcomes v2` or with revision date); emailed to Ultimus.
- **Notes:** Conduct a line-by-line review of budget-to-actuals year-to-date. For each category: Is actual above/below budget? Is the variance one-time or ongoing? Any known upcoming costs not in the original budget? Revise remaining months accordingly. Share with Andi via Slack for approval before sending to Ultimus.

### Core Step 4 — Year-End Budget Right-Sizing (December)
- **Inputs:** (1) YTD monthly financial statements (Jan–Nov). (2) Most recent budget version on SharePoint. (3) Updated knowledge of remaining year-end expenses.
- **Where inputs come from:** Monthly financials on SharePoint; current budget on SharePoint; business-activity updates from the COO.
- **Software & tools:** Microsoft Excel (SharePoint); Slack (Andi's approval); Email (Outlook, to send to Ultimus).
- **Who is responsible:** Finance & Operations Associate and COO (build revision together); Andi (approves); Associate (sends to Ultimus).
- **Outputs:** Final revised budget projecting accurate year-end financials, approved by Andi and sent to Ultimus.
- **Where outputs go:** Saved to SharePoint (versioned or dated); emailed to Ultimus.
- **Notes:** Time-sensitive — Maycomb needs a close-to-final year-end view to calculate and pay tax estimates before December 31. Finish early enough in December for Andi's approval and Ultimus's incorporation. Follow the same review process as Step 3. Once the year closes, Ultimus produces finalized year-end financials, which become the actuals baseline for the next January build (loops to Step 1).

### File Naming & Storage (from SOP)
- Annual budget (Excel): `FY[Year] Budget Maycomb Outcomes`.
- Mid-year / year-end revised budget: `FY[Year] Budget Maycomb Outcomes v2` (or add revision date).
- Monthly financial statements: `[Month] [Year] MOutcomes FS`.

### Exception Handling (from SOP)
- **Major unplanned mid-year expense** → assess with the COO whether an ad-hoc Ultimus update is needed now vs. waiting; if it materially affects year-end projections, send promptly.
- **Monthly financials late/missing** → follow up with Ultimus by email; never skip the monthly review.
- **Unexplained large variance** → discuss with the COO before flagging to Ultimus (could be timing, miscategorization, or real overspend).
- **Andi unavailable** → escalate to another partner, especially in December.

---

# Workflow 5 — Deal Sourcing & Capital Deployment *(PLACEHOLDER — not yet mapped)*

**Status:** Not yet SOP-mapped. Identified as a value driver on the July 7, 2026 call with Ariella Rotenberg and Martina Madrid Sebring — see [[20260616_discovery-brief-maycomb-capital]] Section 11, VD-1.
**What we know so far:** Two-person deal teams per portfolio company; diligence process is a named value driver; underwriting gate requires borrowers to already have outcome-measurement systems in place; field/market-building work (e.g., government/county engagement) treated as adjacent to sourcing even without direct deal outcomes.
**Next step:** Scope with the deal team (likely via Martina) to map sourcing → diligence → structuring → close as an actual spine, the way Workflows 1–4 are mapped from SOPs.

---

# Workflow 6 — Investor Relations & Capital Raising *(PLACEHOLDER — not yet mapped)*

**Status:** Not yet SOP-mapped. Identified July 7, 2026 — see [[20260616_discovery-brief-maycomb-capital]] Section 11, VD-3.
**What we know so far:** Distinct from but related to the deal/investment workflow. Rough structure per Ariella: (1) wholesale marketing/positioning (conferences, collateral, value proposition), (2) bespoke sales process per investor, (3) structuring & closing, (4) ongoing investor relationship management and reporting. Fund Two fundraising is complete; current focus is relationship nurturing and sourcing future investors.
**Next step:** Scope with Ariella (light-touch, if available) or Martina/deal team once further along in the transition.

---

# Workflow 7 — Borrower Asset Management / Portfolio Support *(PLACEHOLDER — not yet mapped)*

**Status:** Not yet SOP-mapped. Identified July 7, 2026 — see [[20260616_discovery-brief-maycomb-capital]] Section 11, VD-2.
**What we know so far:** Support intensity varies widely by borrower — some need minimal touch (already have strong reporting infrastructure), others need deep support (financial management, revenue booking, navigating difficult periods). Framed as an ongoing "client success" function, similar in spirit to a tech company's customer success team.
**Next step:** Scope with the deal team — likely needs borrower-tier segmentation (low-touch vs. high-touch) before a single workflow spine makes sense.

---

# Workflow 8 — Outcome Data Collection & Annual Impact Reporting *(PLACEHOLDER — not yet mapped; see P-007)*

**Status:** Not yet SOP-mapped, but the clearest and most concretely painful of the new value-driver items — promoted to Problem Register **P-007** in [[20260616_discovery-brief-maycomb-capital]] Section 7. See also Section 11, VD-4.
**What we know so far:** Portfolio companies already measure outcome data (required as an underwriting prerequisite), but transferring that data into Maycomb's annual impact report (published end of Q1) is manual and, per Ariella directly, unnecessarily difficult. Maycomb's new Investor Relations hire starts **August 3, 2026** and is expected to make overhauling impact measurement/management and the report itself his first major project — natural point to scope this workflow properly once he's onboarded.
**Next step:** Revisit once the Investor Relations hire is onboarded and has initial thoughts on the current process; map the current data-collection-to-report pipeline the same way Workflows 1–4 were mapped from SOPs.

---

# Overall Workflow (Placeholder — to be strung together)

Once each spine is on the canvas, the **Overall** flow links them where they actually connect (all seams confirmed in the SOPs):

`W1 Legal Bills → W2 AP Run` — **strongest seam.** Legal bills are fronted by the Management Company via the AP run (W1 Core Step 6 → W2 Step 1). Scenario-C bills wait at the W1 reimbursement gate until covering cash lands, *then* enter the AP run.

`W2 AP Run → W4 Budget-to-Actuals` — AP allocations are the actual expense data Ultimus uses to build the monthly budget-to-actuals page (W2 Step 4 allocations → W4 Step 2 monitoring). Correct allocation in W2 is what makes W4's variance review meaningful. *(Both SOPs cross-reference each other under Related SOPs.)*

`W3 Borrower Invoicing → W4 Financial Picture` — borrower interest/principal is the revenue side; payment tracking (W3 Step 5) feeds the broader financial picture W4 monitors. *(W3 and W4 SOPs cross-reference each other.)*

`W1 Quarterly Reconciliation ↔ Fund "Due From" settlement` — the W1 Core Step 7 quarterly allocation review runs **before** Due-to-Manager balances are paid, tying legal-bill allocation accuracy to the inter-entity cash settlement that also underlies W2 allocations.

> Build note: the Overall spine is **not** a fifth workflow — it's the join of the four spines at these seams, with the entity/allocation structure (see Cross-Workflow Foundations) as the shared backbone. The AP Run is the central hub: W1 feeds into it, and it feeds W4.
>
> **Note (July 7, 2026):** Workflows 5–8 (deal sourcing, investor relations, borrower asset management, outcome data/impact reporting) are revenue-side and not yet integrated into this seam map — they don't currently touch the back-office entity/allocation backbone the way W1–W4 do. Revisit once they're scoped.

---

# Cross-Workflow Observations — Structural Context

Not workflow steps — structural and organizational dynamics (confirmed on the 2026-06 call and in the SOPs) that affect how the four workflows execute.

1. **The dual-tracking redundancy (AP Run).** Maycomb keeps a full internal invoice tracker *and* Ultimus keeps its own list, solely so the two can be reconciled (W2 Steps 2 + 4). This evolved historically — Danielle's predecessor didn't track on Maycomb's side, inconsistencies appeared, so Danielle added a parallel tracker. JC flagged that a **shared mailbox** (a single forwarded invoice stream as the master record) could collapse the duplication and ease the Varenka transition — a confirmed, low-cost, no-AI quick win Barry can implement. It persists today mostly because it's how it was always done.

2. **No transactional bank access by design.** Maycomb has View Only in Wells Fargo; Ultimus sets up payments and Maycomb's two-approver release is the only Maycomb-side action on the money. Deliberate cash control, *not* a target for removal — but it means the AP run's slowest segments (approval nudging, two-approver release) are structural; automation can only speed the coordination around them, not the controls.

3. **Approver-name reconciliation needed.** The SOPs name **Andi** (legal discretionary allocations; all budget approvals) and **Miljana** (AP run, "previously Ariella"). The transcript names **Ariella → Miljana** for AP and **"Andy"** for unclear legal calls. Whether Andi/Andy is one person distinct from Ariella and Miljana, and which decisions each owns post-transition, needs confirming before any approval-routing automation. `[TO CONFIRM]`

4. **Institutional knowledge concentration + transition.** The judgment in W1 Core Step 4 (which allocation scenario), the W3 loan-servicing-model figure verification, and the W4 variance interpretation currently live in two departing heads (Danielle end of June; Ariella July 10). The SOPs were authored specifically to externalize this — two of the three operational SOPs were generated using Claude's transcript-to-SOP tool, a working AI use case Danielle found highly effective. SOP capture is the bridge; Varenka (AP run) and the incoming Analyst / Director of Finance & Ops inherit the rest.

5. **Net effect on the automation plan.** The four workflows are unusually well-documented for a 12-person firm (the SOPs are detailed and recent), which lowers automation risk. The highest-leverage moves map directly to the discovery brief's Problem Register: the shared-mailbox/dual-track collapse (P-003), templated invoice generation (P-002), legal-bill allocation rules + reimbursement-gate tracking (P-001), and budget variance-flagging (P-004, Ariella-owned). None of the structural controls (two-approver release, View Only bank access, deal-team final authority) should be automated away — they're the firm's financial guardrails.

---

# `[TO CONFIRM]` Checklist — Next Discovery Pass

Grouped for an efficient interview (Danielle through her part-time period; Varenka as she assumes the AP run; Ariella/Andi for the approval layer before July 10).

**Approval layer (cross-workflow)**
- Reconcile Andi (SOPs) vs "Andy" (transcript) vs Ariella vs Miljana — who is who, and which decisions each owns after the transition.
- Channel for Andi's monthly Partnership Expenses legal-allocation review (email vs Slack).
- Confirm the W1 discretionary-Fund routing (Andi) vs the transcript's deal-level routing (deal team) — different cut-points or a genuine conflict?

**Legal Bills (W1)**
- Tracking mechanism for the Scenario-C reimbursement gate (which Legal Bills Tracker columns; how reminders are set).
- The exact legal-cost limit/cap logic per fund (Fund II cap referenced in transcript) — where documented, who maintains it.

**AP Run (W2)**
- Ultimus Leverpoint's exact legal name and primary day-to-day contact.
- Whether the shared-mailbox change is adopted (and if so, whether the internal tracker is retired or kept as backup).

**Quarterly Invoicing (W3)**
- How many legacy borrowers remain off the quarterly cadence.
- Whether principal/fee amounts are reliably in the loan servicing model or routinely need deal-team confirmation.

**Budget (W4)**
- Confirm Andi owns budget approval; reconcile with the COO collaboration role and Ariella's historical ownership. *(Partly resolved: the Budget SOP confirms Andi (Managing Partner) approves all budgets and the COO co-builds — see `SOPs/Maycomb_Capital_Budgeting_SOP` §3.)*
- The variance-threshold logic Ariella applies in her deep review (needed for the P-004 automation) — the SOP documents the *process* but not her specific numeric thresholds; capture from Ariella before July 10 if the P-004 build proceeds. *(Discovery brief notes she floated >50% and >$10,000 — confirm.)*

**Loan servicing software (future, cross-workflow)**
- Status of the paused loan-servicing-software evaluation (borrower portal + auto-invoicing) — confirmed ~1 year out; revisit timing.

---

*End of current-state map. Source SOPs preserved in full in the `SOPs/` subfolder. Next artifact: visual linear flow per workflow on the canvas, then the Overall flow joining the four spines at the confirmed seams (W1→W2→W4; W3→financial picture), with the entity/allocation structure as the shared backbone.*
