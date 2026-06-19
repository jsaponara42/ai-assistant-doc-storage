---
title: Capital Financing — Current State Workflow Map
date: 2026-06-16
tags:
  - client
  - project
ai: claude
status: needs-attention
---

# Current State Workflow Map — Capital Financing

**Ghost.Ops | AI & Automation Advisory | Phase One Discovery Artifact**

> **Purpose.** Maps the *current* (as-is) state of Capital Financing's five key workflows so each can be rendered as a single **left-to-right linear flow** on the canvas. Each workflow below is one horizontal spine of **core steps**, sequenced left → right. Under each core step are its **sub-steps / details** — what goes in, what comes out — which become the cards that hang off that step on the canvas.
>
> **Structure for the canvas.** Read the numbered core steps as the horizontal spine (Core Step 1 → 2 → 3 …). Each core step's bullet list is the detail stack for that node. A later **"Overall" workflow** will string these five spines together end-to-end.
>
> **Color/type tagging is intentionally omitted** — colors come from implementation tracking later, not from this map.
>
> **Source basis.** [[20260612_discovery-brief-capital-financing]] and the first intro call transcript. Anywhere the source doesn't pin down a step, field, owner, or hand-off, it's marked **`[TO CONFIRM]`** — these double as the next-pass interview checklist (primary conduit: Christy; Kaz for CRM mechanics).
>
> **As-is, including dysfunction.** Breakpoints (manual gaps, failure modes) are marked **⚠** where they exist today. Fixes are not designed here.

---

## Legend

- **Core Step** — a node on the horizontal spine.
- **→** — sequence / hand-off to the next step.
- **In / Out** — data, document, or trigger consumed / produced by a step.
- **Owner** — role responsible. 
- **System** — where it happens.
- **`[TO CONFIRM]`** — not specified in source; verify next pass.
- **⚠** — known breakpoint / friction in the current state.

---

# Workflow Index

| #   | Workflow                             | Spine (core steps, left → right)                                           | Final Deliverable                    |
| --- | ------------------------------------ | -------------------------------------------------------------------------- | ------------------------------------ |
| 1   | Plaintiff / Pre-Settlement Financing | Referral → Intake → Docs → Underwrite → Offer → Execute → Disburse → Track | Funded advance to plaintiff          |
| 2   | Case Expense Financing               | Request → Intake → Underwrite → Agreement → Execute → Pay Vendor → Track   | Vendor paid / firm reimbursed        |
| 3   | Outbound Email & Social Cadence      | Source List → Prepare → Send → Handle Replies → Thank-Yous → Social        | Sent outreach + handled responses    |
| 4   | Sales Consultant Lead Handling       | Lead In → Assign → Follow-Up → Progress → Log → Close                      | Worked lead logged in CRM            |
| 5   | Conference Marketing                 | Select Event → Attend → Capture → Segment → Assign Follow-Up               | Segmented list handed to consultants |

---

# Workflow 1 — Plaintiff / Pre-Settlement Financing

**Spine:** `Referral → Intake → Docs → Underwrite → Offer → Execute → Disburse → Track`

**Trigger:** Attorney/client referral indicates a plaintiff needs a pre-settlement advance.
**Final deliverable:** Funded, executed cash advance disbursed to the plaintiff and recorded, with repayment tracked to settlement.

### Core Step 1 — Referral Received
- **In:** Inbound referral from PI attorney or client contact. `[TO CONFIRM: channel — email, phone, web, consultant relay]`
- **Out:** New plaintiff funding opportunity. `[TO CONFIRM: Salesforce record created now, or email-only until later?]`
- **Owner/System:** `[TO CONFIRM]` / Email
- **⚠** Intake runs on emailed templates, not CRM forms — referral may never become structured CRM data at entry.

### Core Step 2 — Intake Collected
- **In:** Plaintiff + case details. `[TO CONFIRM: required fields — plaintiff identity/contact, attorney/firm, case type, accident date, defendant/insurer, requested amount, est. settlement value, liens]`
- **Out:** Completed intake packet. `[TO CONFIRM: format — emailed template, PDF, CRM record]`
- **Owner/System:** `[TO CONFIRM]` / Emailed templates
- **⚠** Manual, template-driven; no validation; quality depends on sender.

### Core Step 3 — Case Docs Gathered
- **In:** Supporting docs requested from firm. `[TO CONFIRM: which — police report, medical records, demand package, policy limits, representation confirmation]`
- **Out:** Assembled underwriting file.
- **Owner/System:** Underwriting (Christy) / `[TO CONFIRM: email, shared drive, Mighty]`
- **⚠** `[TO CONFIRM: document chase / follow-up with firms a manual bottleneck?]`

### Core Step 4 — Underwriting Assessment
- **In:** Underwriting file; case merits; est. settlement value; existing liens.
- **Out:** Decision (approve / decline / conditional) + approved advance amount. `[TO CONFIRM: criteria / scoring / checklist]`
- **Owner/System:** Christy (Sr. Underwriter) / `[TO CONFIRM: Mighty, spreadsheet, judgment]`. `[TO CONFIRM: approval authority thresholds]`
- **⚠** `[TO CONFIRM: logic documented or held in Christy's head]` — PO-001 single-point-of-failure.

### Core Step 5 — Offer / Agreement Issued
- **In:** Approved amount + terms (fees terminate 12 mo, 1x max multiple, no compounding).
- **Out:** Funding agreement sent to plaintiff/attorney for signature.
- **Owner/System:** `[TO CONFIRM]` / `[TO CONFIRM: e-sign platform, emailed PDF]`

### Core Step 6 — Agreement Executed
- **In:** Signed agreement returned. `[TO CONFIRM: attorney acknowledgment / lien letter required?]`
- **Out:** Fully executed funding agreement.
- **Owner/System:** `[TO CONFIRM]` / `[TO CONFIRM]`

### Core Step 7 — Disbursement
- **In:** Executed agreement; plaintiff payment details.
- **Out:** Funds disbursed; advance recorded against the case.
- **Owner/System:** `[TO CONFIRM: finance/ops]` / Mighty `[TO CONFIRM]`
- **⚠** Mighty is static, no API, no Salesforce integration — funding records don't flow to the CRM.

### Core Step 8 — Record-Keeping & Repayment Tracking
- **In:** Funded terms; settlement timeline.
- **Out:** Advance tracked to settlement; repayment recovered at settlement. `[TO CONFIRM: how settlement status is monitored, by whom]`
- **Owner/System:** `[TO CONFIRM]` / Mighty `[TO CONFIRM]`

---

# Workflow 2 — Case Expense Financing

**Spine:** `Request → Intake → Underwrite → Agreement → Execute → Pay Vendor → Track`

**Product note:** The growth engine — non-recourse funding for case costs (experts, depositions, medical records); pays vendors directly or reimburses the firm; no guarantee, no credit check; repayable only at settlement.
**Trigger:** A law firm needs case costs funded on an active matter.
**Final deliverable:** Vendor paid (or firm reimbursed) for approved expenses, recorded against the matter and tracked to settlement.

### Core Step 1 — Firm Request Received
- **In:** Firm requests case-expense funding on a matter. `[TO CONFIRM: channel; existing relationship vs. cold referral]`
- **Out:** Case-expense opportunity. `[TO CONFIRM: CRM record created?]`
- **Owner/System:** `[TO CONFIRM]` / `[TO CONFIRM]`

### Core Step 2 — Case & Expense Details Collected
- **In:** Case info + specific expenses. `[TO CONFIRM: required fields — matter identity, attorney, expense type(s), vendor(s), amounts, est. settlement value]`
- **Out:** Funding request packet.
- **Owner/System:** Underwriting / `[TO CONFIRM]`
- **⚠** `[TO CONFIRM: likely same manual template intake as W1]`

### Core Step 3 — Underwriting / Approval
- **In:** Case merits; expense schedule; est. settlement value.
- **Out:** Approval + approved amount per expense/vendor. `[TO CONFIRM: criteria, authority thresholds]`
- **Owner/System:** Christy (Sr. Underwriter) / `[TO CONFIRM]`
- **⚠** `[TO CONFIRM: documented criteria vs. judgment — PO-001 risk]`

### Core Step 4 — Funding Agreement Issued
- **In:** Approved terms (non-recourse, repayable at settlement).
- **Out:** Case-expense agreement sent to firm.
- **Owner/System:** `[TO CONFIRM]` / `[TO CONFIRM]`

### Core Step 5 — Agreement Executed
- **In:** Signed agreement returned from firm.
- **Out:** Executed agreement authorizing disbursement.
- **Owner/System:** `[TO CONFIRM]` / `[TO CONFIRM]`

### Core Step 6 — Vendor Payment / Firm Reimbursement
- **In:** Executed agreement; vendor invoices / firm expense docs. `[TO CONFIRM: how invoices are received and verified]`
- **Out:** Payment to vendor directly, or reimbursement to firm.
- **Owner/System:** `[TO CONFIRM: finance/ops]` / Mighty `[TO CONFIRM]`
- **⚠** Mighty isolation — no automated flow of payment data to CRM or firm-relationship records.

### Core Step 7 — Record-Keeping & Repayment Tracking
- **In:** Funded expense amounts; settlement timeline.
- **Out:** Expenses tracked to settlement; repayment recovered at settlement.
- **Owner/System:** `[TO CONFIRM]` / Mighty `[TO CONFIRM]`

---

# Workflow 3 — Outbound Email & Social Cadence

**Spine:** `Source List → Prepare → Send → Handle Replies → Thank-Yous → Social`

**Operator note:** Julius (offshore contractor, $2,500/mo). 3 pre-settlement + 3 case-financing template emails on intervals; manual. Near-zero response; negligible social engagement. **Flagged to collapse/reposition once Salesforce automation lands** — map now as transitional.
**Trigger:** Recurring outbound schedule; new prospects; referral events to acknowledge.
**Final deliverable:** Daily outbound sent, referral thank-yous issued, social posts published, responses handled.

### Core Step 1 — Prospect List Sourced
- **In:** Contacts to email. `[TO CONFIRM: source — Salesforce segmented lists, separate spreadsheet, or manual]`
- **Out:** Working list for the day's sends.
- **Owner/System:** Julius / `[TO CONFIRM]`. `[TO CONFIRM: who supplies/refreshes the list]`
- **⚠** `[TO CONFIRM: list hygiene / dedupe / suppression of already-contacted prospects]`

### Core Step 2 — Template Selection & Personalization
- **In:** Pre-built templates (3 pre-settlement, 3 case-financing) + interval logic.
- **Out:** Outbound email ready to send. `[TO CONFIRM: personalization vs. straight template]`
- **Owner/System:** Julius / `[TO CONFIRM: email platform/inbox]`

### Core Step 3 — Manual Send (70–90/day)
- **In:** Ready emails; daily volume target.
- **Out:** Emails sent — manually, 70–90/day.
- **Owner/System:** Julius / Manual email. `[TO CONFIRM: single inbox / deliverability risk]`
- **⚠** Fully manual high-volume sending; near-zero response; sender-reputation risk at this volume `[TO CONFIRM]`.

### Core Step 4 — Response Handling
- **In:** Inbound replies.
- **Out:** Replies responded to / routed. `[TO CONFIRM: logged in Salesforce or inbox-only? Where do hot replies route?]`
- **Owner/System:** Julius / Manual email.
- **⚠** No confirmed link between replies and CRM — interested prospects may never become tracked opportunities.

### Core Step 5 — Referral Thank-Yous
- **In:** Notification that a lawyer referred a client. `[TO CONFIRM: how Julius learns a referral occurred]`
- **Out:** Thank-you email to the referring lawyer.
- **Owner/System:** Julius (engagement function) / Manual email.

### Core Step 6 — Social Media Posting
- **In:** Content/posts for firm/CEO channels. `[TO CONFIRM: platforms, content source]`
- **Out:** Published social posts.
- **Owner/System:** Julius / Manual. `[TO CONFIRM]`
- **⚠** Engagement negligible.

---

# Workflow 4 — Sales Consultant Lead Handling

**Spine:** `Lead In → Assign → Follow-Up → Progress → Log → Close`

**Context:** CEO is #1 salesperson + default sales manager; hands warm leads to consultants. Team under-follows-up and under-converts; consultants resist CRM notes; sales side unmanaged.
**Trigger:** A warm lead exists (CEO, conference, referral, or inbound) to be assigned.
**Final deliverable:** A worked lead with its outcome (converted / in-pipeline / dead) logged in Salesforce.

### Core Step 1 — Lead Generated
- **In:** New warm lead. `[TO CONFIRM: sources — CEO relationships, conference contacts, referrals, outbound replies]`
- **Out:** Lead/contact exists. `[TO CONFIRM: created in Salesforce auto or manual]`
- **Owner/System:** CEO / Salesforce (contact-by-consultant assignment exists in build).

### Core Step 2 — Lead Assigned to Consultant
- **In:** Lead + assignment logic.
- **Out:** Lead owned by a named consultant (Audrey, Victoria, Brian, Lisa…).
- **Owner/System:** CEO (default sales manager) / Salesforce. `[TO CONFIRM: assignment rules vs. ad-hoc]`
- **⚠** Assignment is CEO-driven and manual; no managed routing layer.

### Core Step 3 — Consultant Follow-Up
- **In:** Assigned lead; segmented list (e.g., post-conference).
- **Out:** Follow-up attempts (calls/emails). `[TO CONFIRM: expected cadence — none currently defined]`
- **Owner/System:** Consultant / `[TO CONFIRM: Salesforce activities, personal email/phone]`
- **⚠** Consultants not following up on segmented lists; no activity minimums, no reporting cadence, no pipeline ownership.

### Core Step 4 — Pipeline Progression
- **In:** Prospect responses; qualification.
- **Out:** Opportunity advanced through stages. `[TO CONFIRM: do defined stages exist today, or is stage structure absent? Brief implies it's a target, not current.]`
- **Owner/System:** Consultant / Salesforce.
- **⚠** No visible/managed stage structure; CEO lacks pipeline visibility.

### Core Step 5 — CRM Logging
- **In:** Activity + outcome data.
- **Out:** Notes, activities, status recorded in Salesforce.
- **Owner/System:** Consultant / Salesforce.
- **⚠** Consultants resist notes; logging inconsistent (no standard ties to what's recorded); reports built but never opened.

### Core Step 6 — Outcome / Close
- **In:** Final disposition.
- **Out:** Lead marked converted (→ funding W1/W2), in-pipeline, or dead. `[TO CONFIRM: hand-off mechanism from closed sales lead into funding intake]`
- **Owner/System:** Consultant / CEO / Salesforce.
- **⚠** `[TO CONFIRM: the bridge from "sales closed" to "funding intake begins" is undocumented — likely the seam connecting W4 → W1/W2 in the Overall flow]`

---

# Workflow 5 — Conference Marketing

**Spine:** `Select Event → Attend → Capture → Segment → Assign Follow-Up`

**Context:** ~$20K/event; multi-state, no outreach state-line restriction; heavy CEO travel season approaching. Post-event lists meant to be segmented and followed up — but consultants aren't working them.
**Trigger:** Capital Financing attends/sponsors a PI conference.
**Final deliverable:** A segmented post-event contact list handed to consultants (feeds Workflow 4).

### Core Step 1 — Event Selection & Commitment
- **In:** Candidate conferences; budget (~$20K/event). `[TO CONFIRM: selection criteria, decider]`
- **Out:** Committed event + spend.
- **Owner/System:** CEO / `[TO CONFIRM]`
- **⚠** ROI vs. ~$20K spend is a watch metric — not currently measured against structured sales output.

### Core Step 2 — Event Logistics & Attendance
- **In:** Confirmed event; travel; materials.
- **Out:** CEO/team attends; in-person contacts made.
- **Owner/System:** CEO (conference logistics is one of his four jobs) / Manual. `[TO CONFIRM: who else supports]`
- **⚠** CEO is the logistics operator — bandwidth drain flagged in brief.

### Core Step 3 — Contact Capture at Event
- **In:** Cards / badge scans / conversations. `[TO CONFIRM: capture method]`
- **Out:** Raw list of new contacts.
- **Owner/System:** CEO / team / `[TO CONFIRM]`
- **⚠** `[TO CONFIRM: how raw contacts reach Salesforce — manual entry, bulk import, or not at all]`

### Core Step 4 — Contact Loading & Segmentation
- **In:** Raw event contacts.
- **Out:** Segmented lists in Salesforce (segmentation + list-email capability exist in build).
- **Owner/System:** `[TO CONFIRM: CEO, Kaz, or consultant]` / Salesforce.

### Core Step 5 — Assignment & Follow-Up
- **In:** Segmented post-conference list.
- **Out:** Lists assigned to consultants → feeds Workflow 4.
- **Owner/System:** CEO → consultants / Salesforce.
- **⚠** Primary documented failure point: consultants don't follow up, so the ~$20K spend doesn't convert.

---

# Overall Workflow (Placeholder — to be strung together)

Once each spine above is on the canvas, the **Overall** flow links them end-to-end. The likely connective seams (all `[TO CONFIRM]`):

`W5 Conference → W4 Sales Handling` — segmented event lists feed consultant follow-up (W5 Step 5 → W4 Step 1).
`W3 Outbound → W4 Sales Handling` — interested replies should become tracked leads (W3 Step 4 → W4 Step 1). ⚠ link not confirmed today.
`W4 Sales Handling → W1 / W2 Funding` — a closed firm/plaintiff triggers funding intake (W4 Step 6 → W1 Step 1 / W2 Step 1). ⚠ **the undocumented bridge** — the single most important seam to define.
`W1 / W2 → (loop back)` — funded relationships feed referral thank-yous and repeat case-expense requests, reinforcing the stickier firm relationships.

> Build note: the Overall spine is **not** a sixth workflow to map from scratch — it's the join of the five existing spines at these seams. Confirm each seam's actual hand-off mechanism before drawing the connectors.

---

# `[TO CONFIRM]` Checklist — Next Discovery Pass

Grouped for an efficient interview (Christy for underwriting/finance; Kaz for CRM mechanics).

**Funding intake & underwriting (W1, W2)**
- Exact required intake fields (plaintiff + case-expense)
- Required supporting documents and how they're chased
- When a Salesforce record is created vs. email-only
- Underwriting criteria/scoring — documented or judgment-based
- Approval authority thresholds and sign-off
- Disbursement mechanics and system of record in Mighty
- How settlement status and repayment are monitored

**Outbound cadence (W3)**
- Prospect list source and who refreshes it
- Email platform/inbox; deliverability setup
- Whether replies are logged in Salesforce and how hot replies route
- How Julius is notified of referrals to trigger thank-yous
- Social platforms and content source

**Sales handling & conferences (W4, W5)**
- Whether defined pipeline stages exist in Salesforce today
- Lead assignment rules vs. ad-hoc CEO assignment
- Current activity expectations (if any)
- Conference contact capture method and import path to Salesforce

**Overall seams**
- The hand-off from closed sales lead → funding intake (W4 → W1/W2)
- Whether outbound replies (W3) connect to the CRM lead flow (W4)

---

*End of current-state map. Next artifact: visual linear flow per workflow on the canvas, then the Overall flow joining the five spines.*
