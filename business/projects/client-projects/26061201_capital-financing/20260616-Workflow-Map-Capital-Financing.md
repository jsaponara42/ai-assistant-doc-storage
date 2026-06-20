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
> **Source basis.** [[20260612_discovery-brief-capital-financing]], the first intro call transcript (Howie + John-Carlos), a 2026-06 ops call between Christy and Josh, and Christy's process-trunk roster. Anywhere the source doesn't pin down a step, field, owner, or hand-off, it's marked **`[TO CONFIRM]`** — these double as the next-pass interview checklist (primary conduit: Christy; Kaz for CRM mechanics).
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

# Process Trunks & Ownership (Christy's side)

**Source: Christy's process-trunk roster.** These are the main operational trunks on the funding/operations side of the business, with current staff ownership. The five workflow spines above are the *front-of-house* flow (how a case or lead comes in and gets funded); these trunks are the *back-of-house* operations that carry a funded deal through to repayment. Several trunks map directly onto the later Core Steps of Workflows 1 and 2 (which were previously `[TO CONFIRM]` for ownership) and are cross-referenced there.

| Trunk | Owner(s) | Maps onto |
| --- | --- | --- |
| **Intake Support** | Rayna (intake lead); Alejandro | Shared Sub-Layer; W1/W2 Intake + Docs steps |
| **Underwriting** | Christy (only) | Shared Sub-Layer Sub-Step B; W1 Step 4 / W2 Step 3 |
| **Contracting** | Yasmin — with Audra, Chanel, Diana | W1 Steps 5–6 / W2 Steps 4–5 (agreement issue + execution) |
| **Funding** | Danielle, Audra | W1 Step 7 / W2 Step 6 (disbursement / vendor payment) |
| **Accounts Receivable** | Jalicia, Diana, Chanel (moved off Audra) | W1 Step 8 / W2 Step 7 (record-keeping + repayment tracking) |
| **Collections** | Yasmin | Post-funding repayment recovery (not yet a mapped spine) |
| **Payoffs** | Diana, Jalicia, Audra, Chanel, Yasmin | Settlement-time repayment resolution (not yet a mapped spine) |

**Notes on the roster:**
- **Underwriting is Christy alone** — confirms the PO-001 single-point-of-failure at the trunk level, not just within a single workflow step. Everything else has at least two people; underwriting has one.
- **Intake support staff are Rayna (lead) and Alejandro.** Note: "Leifert," named in the 2026-06 ops call as part of the Tier 1 underwriting-training discussion alongside Rayna, does not appear on this trunk roster. `[TO CONFIRM: is Leifert the same person as Alejandro under a different name, a separate person, or no longer in this seat? The ops-call references to Rayna/Leifert and the roster's Rayna/Alejandro need reconciling.]`
- **Audra appears across four trunks** (Contracting, Funding, Payoffs) but was explicitly *removed* from Accounts Receivable. This matches the 2026-06 ops call's account of work being repeatedly taken off Audra. `[TO CONFIRM: is Audra overloaded, being narrowed deliberately, or being managed out of certain functions?]`
- **Yasmin owns both Contracting and Collections** and also appears in Payoffs — a heavy concentration on the back end, and the same Yasmin who (per the ops call) sits partly outside Christy's direct management authority. Relevant to any automation touching contracting, collections, or payoffs.
- **Two trunks — Collections and Payoffs — are not yet represented as workflow spines** above. They are post-funding repayment functions that the current five-workflow map does not cover. See the note in the Overall Workflow section.

---

# Shared Sub-Layer — Intake Support

**Confirmed via 2026-06 ops call (Christy + Josh).** This is not a sixth workflow — it's a shared resource layer that both Workflow 1 (pre-settlement) and Workflow 2 (case expense) draw on at their intake/docs steps. Mapped separately here because the canvas would otherwise show duplicate logic on both spines.

**Roles in this layer:**
- **Christy** — Intake & Underwriting lead. Owns the underwriting assessment for both workflows; the underwriting heuristic and tiering below is hers.
- **Rayna** — Intake Lead, ~4 years tenure, and owner of the **Intake Support** trunk. Currently doing ~98% of the full pre-settlement approval workflow already (per Christy); only the final 2% — communicating the approval/denial decision to the firm — is held back from her.
- **Alejandro** — Intake support, on the Intake Support trunk with Rayna (per Christy's roster).
- **Leifert** — named in the 2026-06 ops call as being trained up on Tier 1 underwriting alongside Rayna, ~3 years tenure. `[TO CONFIRM: Leifert does not appear on Christy's trunk roster (which lists Rayna + Alejandro for Intake); reconcile whether Leifert = Alejandro, a separate person, or no longer in seat.]`
- **Two VAs ($13/hr, contract)** — Hired specifically as intake document-collection support, separate from Rayna/Leifert. Onboarding ~4 weeks in at time of this call. Trained to do internet searches for child support records, bankruptcy discharge records, police reports, IDs, photos, and basic firm-provided information, then enter it into Mighty and Salesforce.
- **Tammy** — Prospective part-time underwriter (10am–2pm M–F), interviewed but not yet vetted/approved to make underwriting decisions; status as of this call is undecided pending a 90-day probationary period. Wants underwriting only, not intake — Christy is resisting Howie's push to also use her for contracting, training, and case-expense onboarding calls, since those overlap with other people's roles (contracting = Yasmin's department; training = Christy's responsibility).

### Sub-Step A — Document Collection (VA layer)
- **In:** Case referred for funding (from W1 Step 1 or W2 Step 1); firm-provided basics.
- **Out:** Collected supporting documents — internet-sourced (child support, bankruptcy discharge records) plus firm-sourced (police reports, IDs, photos) — entered into Mighty and Salesforce.
- **Owner/System:** The two $13/hr VAs / manual research + Mighty + Salesforce data entry.
- **⚠** Confirmed clunky: "a lot of steps... it's a little clunky" — manual, multi-system entry with no automation between research, Mighty, and Salesforce.
- **⚠** This layer exists specifically *because* W1 (pre-settlement) volume has outgrown the core intake team's capacity — it's surge capacity, not a permanent staffing solution as currently scoped.

### Sub-Step B — Underwriting Tiering (Christy's layer)
- **In:** Assembled case file (post Sub-Step A); requested amount.
- **Out:** Routed to the appropriate underwriting tier:
  - **Tier 1 — Basic ($500–$2,000):** Simple formulaic cases — liability clear, accepted, policy limits and medicals straightforward. Currently being trained up to Rayna and Leifert as a growth pathway; costs the company effectively nothing per Howie's own framing ("why do I care if I lose $2,000").
  - **Tier 2 — Complex / high-dollar:** Cases requiring judgment beyond the formula — this is where Christy and a future second underwriter (Tammy, if she works out) operate. Case-expense funding requests frequently run "way out of [Tier 1] range," sometimes into the hundreds of thousands.
- **Owner/System:** Christy (all tiers, oversight); Rayna/Leifert (Tier 1, in training); Tammy (Tier 2, prospective, unvetted).
- **Underwriting heuristic (confirmed):** Christy does not take attorney-provided case facts at face value — "it's not my job to always agree that the attorney is being truthful." Attorneys are financially incentivized to oversell cases since funding is non-recourse (firm keeps the money even if the case loses). Christy performs an assessment pass even on the "simple" tier rather than rubber-stamping attorney representations. This is the underwriting logic that was previously `[TO CONFIRM]` — it is judgment-based, held by Christy, not a documented scoring model.
- **⚠ PO-001 still applies:** the *judgment* (vetting attorney claims) is Christy's alone; Tier 1 formulaic cases are now distributable to Rayna/Leifert, but Tier 2 complex judgment remains single-threaded through Christy pending Tammy's unproven status.

### Sub-Step C — Case-Expense Onboarding Calls (sales-adjacent, currently broken)
- **In:** New case-expense relationship with a law firm.
- **Out:** Firm onboarded with a clear understanding of what Capital Financing needs submitted and how.
- **Owner/System:** Sales team (Audrey and others) / in-person or call-based, no standard format. `[TO CONFIRM: is there a standard onboarding script/checklist, or is it fully ad hoc per consultant?]`
- **⚠ Confirmed breakpoint, not previously documented:** Onboarding is inconsistent person-to-person — "whatever Audrey did in her in-person meeting with one law firm did not transition well." A contact at one firm who was never trained submitted 20 case-expense files in a single day, none formatted correctly, creating a 20-out/20-back-in rework loop between Capital Financing and the firm.
- **⚠** Sales team is explicitly described as weak at these calls ("our sales team, they're not great at this. They're awful at having these calls") — proposed fix (having Tammy support onboarding calls) is unresolved as of this call.

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
- **Owner/System:** Rayna / Leifert (intake team) handle the core packet; the two VAs handle document collection (see **Shared Sub-Layer — Intake Support, Sub-Step A**) / Emailed templates, then Mighty + Salesforce.
- **⚠** Manual, template-driven; no validation; quality depends on sender.
- **⚠ Confirmed (2026-06):** volume spikes break this step. A single untrained firm contact submitted 20 case files in one day with none formatted correctly — see Sub-Step C — triggering a 20-out/20-back-in rework loop. Pre-settlement *volume in* (inquiries, calls, voicemails, partial submissions) is meaningfully higher than *volume approved*, which is the only number currently tracked/reported — so intake load is undercounted at the leadership level.

### Core Step 3 — Case Docs Gathered
- **In:** Supporting docs requested from firm. `[TO CONFIRM: which — police report, medical records, demand package, policy limits, representation confirmation]` Confirmed additions: child support records, bankruptcy discharge records, IDs, photos.
- **Out:** Assembled underwriting file.
- **Owner/System:** The two $13/hr VAs (document collection, confirmed) under Christy's oversight / manual internet research + Mighty + Salesforce entry. See **Shared Sub-Layer — Intake Support, Sub-Step A**.
- **⚠** Confirmed clunky multi-system process — research, then manual entry into both Mighty and Salesforce, no automation between them.

### Core Step 4 — Underwriting Assessment
- **In:** Underwriting file; case merits; est. settlement value; existing liens; requested amount.
- **Out:** Decision (approve / decline / conditional) + approved advance amount.
- **Owner/System:** Tiered — see **Shared Sub-Layer — Intake Support, Sub-Step B**. Tier 1 ($500–$2,000, formulaic) routed to Rayna/Leifert (in training); Tier 2 (complex/high-dollar) held by Christy, with Tammy a prospective but unvetted second underwriter.
- **Underwriting heuristic (confirmed):** Christy assumes attorney-provided facts may be incomplete or inaccurate and are financially incentivized to oversell cases (funding is non-recourse — firm keeps the advance even if the case loses); she performs an independent assessment rather than approving on attorney representation alone. Previously `[TO CONFIRM]`; now confirmed as judgment-based, not a documented scoring model.
- **⚠** `[TO CONFIRM: approval authority thresholds for Tier 1 vs. Tier 2, formally]`
- **⚠ New, confirmed breakpoint:** The CEO has personally intervened directly in live underwriting files — approving or attempting to approve funding before the attorney of record had signed off. This breaks the workflow at Core Step 5 (the attorney/plaintiff must approve funding — "attorneys want to approve the funding") and creates account-risk and team rework. Flagged in **Cross-Workflow Observations** below as a structural, not one-off, issue.
- **⚠** PO-001 single-point-of-failure persists for Tier 2 (Christy alone) pending Tammy's probationary outcome.

### Core Step 5 — Offer / Agreement Issued
- **In:** Approved amount + terms (fees terminate 12 mo, 1x max multiple, no compounding).
- **Out:** Funding agreement sent to plaintiff/attorney for signature.
- **Owner/System:** **Contracting trunk** — Yasmin (owner), with Audra, Chanel, Diana / `[TO CONFIRM: e-sign platform, emailed PDF]`
- **⚠ Confirmed:** Attorney sign-off on funding is required before approval is finalized — this is the step the CEO's direct file intervention (Core Step 4 breakpoint) has bypassed, with account-loss risk as the explicit concern raised internally.

### Core Step 6 — Agreement Executed
- **In:** Signed agreement returned. `[TO CONFIRM: attorney acknowledgment / lien letter required?]`
- **Out:** Fully executed funding agreement.
- **Owner/System:** **Contracting trunk** — Yasmin, with Audra, Chanel, Diana / `[TO CONFIRM: system]`

### Core Step 7 — Disbursement
- **In:** Executed agreement; plaintiff payment details.
- **Out:** Funds disbursed; advance recorded against the case.
- **Owner/System:** **Funding trunk** — Danielle, Audra / Mighty `[TO CONFIRM: payment rails / method]`
- **⚠** Mighty is static, no API, no Salesforce integration — funding records don't flow to the CRM.

### Core Step 8 — Record-Keeping & Repayment Tracking
- **In:** Funded terms; settlement timeline.
- **Out:** Advance tracked to settlement; repayment recovered at settlement. `[TO CONFIRM: how settlement status is monitored, by whom]`
- **Owner/System:** **Accounts Receivable trunk** — Jalicia, Diana, Chanel / Mighty `[TO CONFIRM]`. Settlement-time repayment resolution runs through the **Payoffs trunk** (Diana, Jalicia, Audra, Chanel, Yasmin); overdue recovery escalates to the **Collections trunk** (Yasmin). See Process Trunks table.

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
- **⚠ Confirmed (2026-06):** This step depends on the firm having been properly onboarded first — see **Shared Sub-Layer — Intake Support, Sub-Step C**. Onboarding quality is inconsistent per-consultant, and a poorly onboarded firm contact produces malformed bulk submissions (e.g., 20 in a day) instead of clean individual requests.

### Core Step 2 — Case & Expense Details Collected
- **In:** Case info + specific expenses. `[TO CONFIRM: required fields — matter identity, attorney, expense type(s), vendor(s), amounts, est. settlement value]`
- **Out:** Funding request packet.
- **Owner/System:** Underwriting (Christy) / document collection support per **Shared Sub-Layer — Intake Support, Sub-Step A** where applicable.
- **⚠** Same manual template intake pattern as W1 — confirmed, not just inferred. Case-expense requests are described as frequently "way out of [Tier 1] range," sometimes into the hundreds of thousands — meaning this step usually routes straight to Tier 2 complex underwriting (Christy), bypassing the Rayna/Leifert Tier 1 track entirely.

### Core Step 3 — Underwriting / Approval
- **In:** Case merits; expense schedule; est. settlement value.
- **Out:** Approval + approved amount per expense/vendor.
- **Owner/System:** Christy (Sr. Underwriter) — Tier 2 by default given typical case-expense dollar amounts. See **Shared Sub-Layer — Intake Support, Sub-Step B** for the underwriting heuristic (attorney claims are independently vetted, not taken at face value).
- **⚠** `[TO CONFIRM: formal authority thresholds]` — PO-001 risk is more acute here than in W1, since case-expense amounts skew complex/high-dollar and stay with Christy rather than being distributable to Rayna/Leifert.

### Core Step 4 — Funding Agreement Issued
- **In:** Approved terms (non-recourse, repayable at settlement).
- **Out:** Case-expense agreement sent to firm.
- **Owner/System:** **Contracting trunk** — Yasmin (owner), with Audra, Chanel, Diana / `[TO CONFIRM: system]`

### Core Step 5 — Agreement Executed
- **In:** Signed agreement returned from firm.
- **Out:** Executed agreement authorizing disbursement.
- **Owner/System:** **Contracting trunk** — Yasmin, with Audra, Chanel, Diana / `[TO CONFIRM: system]`

### Core Step 6 — Vendor Payment / Firm Reimbursement
- **In:** Executed agreement; vendor invoices / firm expense docs. `[TO CONFIRM: how invoices are received and verified]`
- **Out:** Payment to vendor directly, or reimbursement to firm.
- **Owner/System:** **Funding trunk** — Danielle, Audra / Mighty `[TO CONFIRM: payment rails / method]`
- **⚠** Mighty isolation — no automated flow of payment data to CRM or firm-relationship records.

### Core Step 7 — Record-Keeping & Repayment Tracking
- **In:** Funded expense amounts; settlement timeline.
- **Out:** Expenses tracked to settlement; repayment recovered at settlement.
- **Owner/System:** **Accounts Receivable trunk** — Jalicia, Diana, Chanel / Mighty `[TO CONFIRM]`. Settlement-time resolution via the **Payoffs trunk**; overdue recovery via **Collections** (Yasmin). See Process Trunks table.

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
- **⚠ Confirmed (2026-06):** Case-expense onboarding calls specifically — a Workflow 4/Shared-Layer crossover point — are weak: "our sales team... they're awful at having these calls." This is a named, confirmed skill gap, not just a process gap. See **Shared Sub-Layer — Intake Support, Sub-Step C**.

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
- **⚠ Confirmed seam detail:** For case-expense specifically, this close step now confirmed to flow into **Shared Sub-Layer Sub-Step C** (firm onboarding) before Workflow 2 Core Step 1 — onboarding quality at this hand-off directly determines whether the firm's future submissions are clean or become rework (see W2 Step 1 breakpoint).

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

Once each spine above is on the canvas, the **Overall** flow links them end-to-end. The likely connective seams (all `[TO CONFIRM]` unless noted):

`W5 Conference → W4 Sales Handling` — segmented event lists feed consultant follow-up (W5 Step 5 → W4 Step 1).
`W3 Outbound → W4 Sales Handling` — interested replies should become tracked leads (W3 Step 4 → W4 Step 1). ⚠ link not confirmed today.
`W4 Sales Handling → Shared Sub-Layer Sub-Step C → W2 Funding` — **confirmed seam for case expense:** a closed firm relationship (W4 Step 6) leads to firm onboarding (Sub-Step C), and onboarding quality directly determines whether the firm's first W2 submission is clean or malformed.
`W4 Sales Handling → W1 Funding` — the pre-settlement equivalent bridge remains **undocumented** — the single most important seam still to define for the plaintiff side.
`W1 / W2 → (loop back)` — funded relationships feed referral thank-yous and repeat case-expense requests, reinforcing the stickier firm relationships.

> Build note: the Overall spine is **not** a sixth workflow to map from scratch — it's the join of the five existing spines (plus the Shared Sub-Layer) at these seams. Confirm each seam's actual hand-off mechanism before drawing the connectors.

**Post-funding tail not yet mapped as spines.** Christy's trunk roster surfaces two operational functions that sit *after* W1 Step 8 / W2 Step 7 and are not yet drawn as workflow spines:
- **Payoffs** (Diana, Jalicia, Audra, Chanel, Yasmin) — resolving repayment at settlement.
- **Collections** (Yasmin) — recovering overdue/at-risk repayments.

These likely warrant their own spine — call it **Workflow 6 — Repayment / Payoffs / Collections** — once mapped, since they're where the money actually comes back and where revenue leakage would show up. `[TO CONFIRM: trigger (settlement notice?), steps, systems, and how a case moves from AR → Payoffs → Collections.]`

---

# Cross-Workflow Observations — Organizational Context

These are not workflow steps. They're governance and management dynamics, confirmed via the 2026-06 ops call, that materially affect *how* the workflows above actually execute day to day. Recorded here because they explain several of the breakpoints already noted in the workflow steps, but they are not themselves automatable process — they're a management/authority layer the AI & automation plan needs to account for, not solve directly.

1. **CEO direct intervention in live underwriting files.** Confirmed, recurring pattern (Christy: "he does this... every single time"): the CEO bypasses the underwriting and attorney-approval steps by entering files directly and attempting to approve funding before the attorney of record has signed off. This creates account-loss risk (attorneys may fire Capital Financing over unauthorized approvals), generates emotional/rework fallout across the team, and undermines the very underwriting structure (tiering, heuristic) documented in the Shared Sub-Layer above. This is the direct cause of the Core Step 4/5 breakpoint flagged in Workflow 1.

2. **Volume is undercounted at the leadership level.** The CEO's volume metric tracks *approved* funding only. Christy's actual workload includes total *inbound* volume — emails, voicemails, calls, partial/incorrect submissions, and the rework loop from poorly onboarded firms — which is materially higher and growing into the firm's busy season. This mismatch is the root cause of recurring staffing disputes (see #3) and likely understates true operating load across Workflows 1, 2, and the Shared Sub-Layer.

3. **Contested authority over intake/underwriting staffing decisions.** A recurring pattern, per Christy, of the CEO proposing a new hire (most recently Tammy) as a wholesale replacement for an existing staffing plan (the two VAs, and the Rayna/Leifert Tier 1 underwriting growth path) rather than as additive capacity — then reversing or denying prior commitments when challenged (e.g., disputing that Tier 1 underwriting training for Rayna/Leifert had ever been promised, twice). Christy frames this as a recurring pattern across multiple past hires, not a one-off. Net effect: staffing plans for the Shared Sub-Layer are unstable and subject to reversal outside the documented growth/tiering structure.

4. **Unclear management authority outside the CEO/Christy reporting line.** A separate department (Yasmin's team, which includes contracting) operates partly outside Christy's ability to manage directly — attempts to manage Yasmin in the past resulted in informal escalation to Danielle (part-owner) and friction that affected Christy's working relationship with the CEO's circle. Danielle has independently made management decisions affecting Yasmin's team (e.g., promoting a team member to manager with an office) without consulting Christy or, per the call, without a clear documented process behind the decision. This is relevant context for any automation work that touches contracting or Yasmin's department, since the actual decision-making authority there is not where the org chart would suggest.

5. **Net effect on the automation plan.** None of the above are workflow inefficiencies that automation fixes directly — they're authority and communication patterns that will determine whether any process change (tiering, onboarding scripts, CRM discipline, etc.) actually sticks once implemented. Worth surfacing explicitly in the opportunity map as a "process governance" risk alongside the technical opportunities, since a clean automated workflow can still be broken by ad hoc file intervention or reversed staffing decisions.

---

# `[TO CONFIRM]` Checklist — Next Discovery Pass

Grouped for an efficient interview (Christy for underwriting/finance; Kaz for CRM mechanics).

**Funding intake & underwriting (W1, W2)**
- Exact required intake fields (plaintiff + case-expense) — partially confirmed; format (CRM vs. email-only) still open
- How supporting docs are chased when a firm is slow to respond
- When a Salesforce record is created vs. email-only
- Formal Tier 1 vs. Tier 2 approval authority thresholds (heuristic confirmed; thresholds not)
- Disbursement mechanics and system of record in Mighty (Funding trunk owners now known: Danielle, Audra)
- How settlement status and repayment are monitored (AR trunk owners now known: Jalicia, Diana, Chanel)

**Process trunks & roster reconciliation**
- Reconcile Leifert (ops call) vs. Alejandro (roster) for the Intake Support trunk — same person, separate, or vacated seat?
- Audra's load: she's across Contracting, Funding, and Payoffs but was removed from AR — overloaded, being narrowed, or managed out?
- Map the post-funding tail (Payoffs, Collections) as Workflow 6: trigger, steps, systems, AR → Payoffs → Collections hand-offs
- Confirm e-sign/contracting system used by the Contracting trunk (Yasmin's team)

**Shared Intake Support layer**
- Standard onboarding script/checklist for case-expense firm onboarding calls — does one exist, or is it fully ad hoc per consultant?
- Tammy's resolution: did the 90-day probationary period happen, and with what scope (underwriting only, per Christy's request)?
- Whether the VA layer is intended to become permanent or is explicitly surge-only

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
- The hand-off from closed sales lead → pre-settlement funding intake (W4 → W1) — still undocumented
- Whether outbound replies (W3) connect to the CRM lead flow (W4)

---

*End of current-state map. Next artifact: visual linear flow per workflow on the canvas, then the Overall flow joining the five spines.*
