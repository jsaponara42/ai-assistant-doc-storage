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
> **Source basis.** [[20260612_discovery-brief-capital-financing]], the first intro call transcript (Howie + John-Carlos), a 2026-06 ops call between Christy and Josh, Christy's process-trunk roster, and CEO strategic conversation (2026-06) on sales accountability, KPI implementation, operations oversight, and staffing performance. Anywhere the source doesn't pin down a step, field, owner, or hand-off, it's marked **`[TO CONFIRM]`** — these double as the next-pass interview checklist (primary conduit: Christy; Kaz for CRM mechanics).
>
> **As-is, including dysfunction.** Breakpoints (manual gaps, failure modes) are marked **⚠** where they exist today. Management/authority dynamics and accountability frameworks that determine execution are documented in **Cross-Workflow Observations** and **Sales Performance & Accountability**. Fixes are not designed here.

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

| #   | Workflow                                                     | Spine (core steps, left → right)                                                             | Final Deliverable                      |
| --- | ------------------------------------------------------------ | -------------------------------------------------------------------------------------------- | -------------------------------------- |
| 1   | Plaintiff / Pre-Settlement Financing                         | Referral → Intake → Docs → Underwrite → Offer → Execute → Disburse → Track                   | Funded advance to plaintiff            |
| 2   | Case Expense Financing                                       | Request → Intake → Underwrite → Agreement → Execute → Pay Vendor → Track                     | Vendor paid / firm reimbursed          |
| 3   | Outbound Email & Social Cadence                              | Source List → Prepare → Send → Handle Replies → Thank-Yous → Social                          | Sent outreach + handled responses      |
| 4   | Sales Consultant Lead Handling                               | Lead In → Assign → Follow-Up → Progress → Log → Close                                        | Worked lead logged in CRM              |
| 5   | Conference Marketing                                         | Select Event → Attend → Capture → Segment → Assign Follow-Up                                 | Segmented list handed to consultants   |
| —   | **Salesforce Daily Routine** (governance layer, not a spine) | Task review → Contact → Follow-up reason → Task lifecycle → Report review → Monthly inactive | Nothing falls through the cracks (CEO) |

---

# Quick-Reference Flowcharts (Arrow Style)

Compact step-by-step view of each workflow — more detail than the Index table above (owner/system + key breakpoints per step), but not the full prose below. Use this section to scan a workflow fast; drop into the numbered sections further down for full detail, sourcing, and `[TO CONFIRM]` context.

**Legend:** `owner / system` in parentheses. `⚠` = confirmed breakpoint. `?` = `[TO CONFIRM]`.

### Shared Sub-Layer — Intake Support (feeds W1 & W2)
Document Collection *(2 VAs / manual research + Mighty + SF)* ⚠ clunky
→ Underwriting Tiering *(Christy — Tier 2; Rayna/Leifert — Tier 1 formulaic $500–2K)*
→ Strategy Call *(FC, +Howie if needed)*
→ Onboarding Call *(FC — Audrey et al.)* ⚠ inconsistent, weak skill, no standard script
→ Follow-up email, 6 attachments *(Christy/FC — Word doc, Kaz's SF automation)* ⚠ core friction point, firms go quiet (want #14 portal in progress)

### Workflow 1 — Plaintiff / Pre-Settlement Financing
Referral Received *(? / Email)* ⚠ not structured CRM data
→ Intake Collected *(Rayna/Leifert / Mighty+SF)* ⚠ manual template, no validation; ⚠ volume spikes break this step
→ Case Docs Gathered *(2 VAs / research + Mighty + SF)* ⚠ clunky multi-system
→ Underwriting Assessment *(Tier 1: Rayna/Leifert; Tier 2: Christy)* ⚠ CEO direct file intervention; approval thresholds? 
→ Offer/Agreement Issued *(Contracting — Yasmin, Audra, Chanel, Diana / JB generates contract → FormStack e-sign, 25% or 5% model)* ⚠ attorney sign-off required — this is the step CEO intervention bypasses
→ Agreement Executed *(FormStack, shared group login → uploaded to JB)*
→ Disbursement *(Funding — Danielle, Audra / push-to-debit via AppPay $2.5K cap, direct deposit, or wire)* ⚠ no Salesforce integration except one manual status flip
→ Record-Keeping & Tracking *(AR — Jalicia, Diana, Yasmine, Chanel / JB, lien)* ⚠ fully manual follow-up, no reminders → **Workflow 6** (payoff/close-out)

### Workflow 2 — Case Expense Financing
Firm Request Received *(Intake / JB, tagged "LIT")* ⚠ depends on onboarding quality upstream; no dedicated case-expense field in JB
→ Acknowledgement Letter *(Contracting / manual ask + follow-up)* ⚠ required before agreement can be sent, no defined reminder cadence
→ Case & Expense Details Collected *(Christy / VA doc support)* ⚠ same manual-template pattern as W1; usually routes straight to Tier 2 (amounts often 6-figure)
→ Underwriting / Approval *(Christy — Tier 2 by default; 15% model)* ⚠ thresholds? — PO-001 risk more acute here
→ Funding Agreement Issued *(Contracting — Yasmin, Audra, Chanel, Diana / JB → FormStack)*
→ Agreement Executed *(FormStack → JB)*
→ Vendor Payment / Firm Reimbursement *(Funding — Danielle, Audra / direct deposit or check only, never push-to-debit)* ⚠ no CRM integration
→ Record-Keeping & Tracking *(AR)* → **Workflow 6** (payoff/close-out)

### Workflow 3 — Outbound Email & Social Cadence
Prospect List Sourced *(Julius / ?)*
→ Template Selection & Personalization *(Julius — 3 pre-settlement + 3 case-financing templates)*
→ Manual Send, 70–90/day *(Julius / manual email)* ⚠ near-zero response, high-volume manual
→ Response Handling *(Julius)* ⚠ no confirmed link to CRM
→ Referral Thank-Yous *(Julius)*
→ Social Media Posting *(Julius)* ⚠ negligible engagement
*(Whole spine flagged to collapse/automate — wants #11, #15)*

### Workflow 4 — Sales Consultant Lead Handling
Lead Generated *(CEO / Salesforce)*
→ Lead Assigned to Consultant *(CEO — manual)* ⚠ no managed routing layer
→ Consultant Follow-Up *(Consultant)* ⚠ inconsistent; no cadence enforced; 1-week post-onboarding target routinely missed (see want #15)
→ Pipeline Progression *(Consultant / Salesforce)* ⚠ no visible/managed stage structure
→ CRM Logging & Task Lifecycle *(Consultant / Salesforce)* ⚠ note-taking resistance; create→schedule→complete→remove lifecycle not standard practice
→ Outcome / Close *(Consultant, CEO / Salesforce)* → feeds **W2 Sub-Step C** (case-expense seam confirmed) / feeds **W1** (pre-settlement seam still undocumented)

### Workflow 5 — Conference Marketing
Event Selection & Commitment *(CEO — ~$20K/event)* ⚠ ROI not measured against sales output
→ Event Logistics & Attendance *(CEO)* ⚠ CEO is the logistics operator — bandwidth drain
→ Contact Capture at Event *(CEO/team / ?)* ⚠ capture → Salesforce path unconfirmed
→ Contact Loading & Segmentation *(? / Salesforce)*
→ Assignment & Follow-Up *(CEO → Consultants)* ⚠ primary documented failure point — spend doesn't convert → feeds **W4 Step 1**

### Salesforce Daily Routine (governance layer — CEO only, touches all workflows)
Plan day/week *(review calendar, book 4+ meetings/day)*
→ Review current/overdue tasks
→ Open task, review notes
→ Reach out (email/phone)
→ Determine follow-up reason (post-strategy vs. post-onboarding)
→ Task bar for conference follow-ups
→ Complete task → create next task (2wk–1mo out) → remove dead tasks
→ Review Top Companies / Top Prospects reports
→ Monthly: review inactive reports (case financing + pre-settlement)
→ Fill unbooked time with inactive-account outreach / prospecting
⚠ Only the CEO currently runs this. Whether it extends to consultants (manual) or gets automated is want #10.

### Post-Funding Tail — now mapped as Workflow 6
AR Tracking *(Jalicia, Diana, Yasmine, Chanel / JB)* ⚠ fully manual, no reminders, discretionary cadence
→ Payoff or Reduction Request *(Yasmine / dedicated payoff inbox)* ⚠ reductions route to Howie for approval
→ Deposit Received *(VA logs it, tags Howie+Danielle, assigns Yasmine)*
→ Reconciled *(Yasmine / JB vs. QuickBooks)*
→ Closed *(Danielle / JB + QuickBooks, logs how it closed)*

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
| **Inactive Account Follow-Up** | Julius (behind the scenes) — **automation candidate** | Monthly CEO review + ongoing Julius outreach for inactive accounts (case financing + pre-settlement). See notes below. |

**Notes on the roster:**
- **Underwriting is Christy alone** — confirms the PO-001 single-point-of-failure at the trunk level, not just within a single workflow step. Everything else has at least two people; underwriting has one. CEO notes: Christy is highly professional, thorough (5–7% bad-debt rate annually), protective of company interests, and extremely conservative in approvals. However, training new intake staff is inefficient (~6 months ramp-up); root cause is free-form Mighty data entry (no structured fields) rather than using pre-built field schema. Christy is open to oversight but asserts "this is the only way to do it" without external validation of assumptions.
- **Julius — Inactive Account Follow-Up (new, from Howie dictation 2026-07-28):** Julius handles follow-up with all inactive accounts (both case financing and pre-settlement) behind the scenes, sending templated emails and calls. He has **not had much success with responses**. He tends to fall **months behind** in his cadence, which defeats the consistency that follow-up requires. The CEO explicitly stated: "This is something I believe can be automated as well, does not need a manual person to be sending out templated emails. And actually, if we had it set up from an automation perspective, it probably would be more creative, more effective, and more consistent, where he seems to fall months behind in his cadences, which defeats the consistency that we're looking for on follow-up emails for whatever the purpose is we're looking for." **This is a high-priority automation candidate** — flagged as ranked want #10 in `xx_howies_wants.md`. Should be mapped as its own Process Trunk: **Inactive Account Follow-Up** (Julius, automated replacement TBD). Currently manual, low-success, cadence-defeated. **Update (2026-08-06 call):** Kaz has explicitly recommended cutting Julius outright rather than repositioning him as a VA — Howie is paying for output that isn't landing results, and Kaz's view is to automate the function and let the role go. Decision still pending with Howie.

- **Intake support staff are Rayna (lead) and Alejandro.** Note: "Leifert," named in the 2026-06 ops call as part of the Tier 1 underwriting-training discussion alongside Rayna, does not appear on this trunk roster. **Likely resolution (cross-referenced against the discovery brief's org chart, 2026-08-XX):** the org chart lists a **"Leaford Grayson"** under Intake, alongside Reyna Carcamo, Myia Strozier, and Alejandro Restrepo — "Leifert" is almost certainly a mishearing/mistranscription of "Leaford" from dictation audio, not a separate or missing person. Treat as probable, not fully confirmed — worth a one-line confirmation with Christy, but no longer a live open question requiring active investigation. Per Christy, Rayna is already doing ~98% of pre-settlement approval workflow; only the final 2% (approval/denial communication to firm) is withheld from her.

- **Audra appears across four trunks** (Contracting, Funding, Payoffs) but was explicitly *removed* from Accounts Receivable. This matches the 2026-06 ops call's account of work being repeatedly taken off Audra. `[TO CONFIRM: is Audra overloaded, being narrowed deliberately, or being managed out of certain functions?]` Suggests possible performance management dynamic or workload balancing in progress.

- **Yasmin owns both Contracting and Collections** and also appears in Payoffs — a heavy concentration on the back end. Per CEO: Yasmin is detail-oriented but weaker in communication and leadership; she is a "follower and doer" rather than a leader. She works closely with Christy and Danielle, handling behind-the-scenes tasks. Yasmin sits partly outside Christy's direct management authority; past attempts to manage Yasmin resulted in informal escalation to Danielle (part-owner). Relevant context for any automation touching contracting, collections, or payoffs, since actual decision-making authority may not follow the org chart.

- **Two trunks — Collections and Payoffs — are not yet represented as workflow spines** above. They are post-funding repayment functions that the current five-workflow map does not cover. See the note in the Overall Workflow section.

**Systems glossary (confirmed via Yasmine walkthrough, 2026-08-XX):**
- **JB = Mighty = Justice Bolt** — same platform, referred to interchangeably by staff; this is the core loan-servicing system where applications, underwriting, contracting, and AR/lien tracking all live.
- **FormStack by Intelistack** — the confirmed e-signature platform for funding agreements. Used with a **single shared login for the whole Contracting group**, not individual per-user accounts — a direct, confirmed contrast with what Segue proposed but never actually demonstrated working live during their own demo.
- **AppPay** — separate app from JB, used for push-to-debit disbursements only (plaintiffs, capped at $2,500 currently).
- **Funding Exchange** — external, cross-funding-company platform used to check for existing liens on a case before advancing money (prevents "stacking"), and to log new liens once funded so other funding companies can see them.
- **Salesforce** — confirmed single touchpoint for Contracting: flipping a record to "Approved" status post-funding-approval (previously triggered marketing drips, currently paused) and adding newly-discovered attorney contacts to a firm's record.

**AR file ownership, confirmed headcount snapshot (2026-08-XX):** Jalicia (VA, part-time) — 323 files; Diana (VA) — 313 files; Yasmine herself — 261 files; Chanel (also Contracting) — 187 files. Updates the earlier "Jalicia, Diana, Chanel" roster — Yasmine personally also carries a significant AR caseload, not just oversight.

- **Danielle** — Part owner, professional, and territorial about her role. Per CEO: "Danielle's a professional. Danielle's a part owner. Danielle's going to be very territorial." However, she supports bringing in external expertise for process improvement and is encouraging Michael (Injury Specialists client) to engage the same advisor. She has made independent management decisions (e.g., promoting a team member) without consulting Christy. **Update (2026-08-06 call):** Howie describes her as personally close ("family to me") and professionally high-level (prior SAP experience). No obvious automation surface in her own function per Howie, but she wants visibility into what's going on across the business. One of the three leadership-team members (with Christy and Yasmin) who told Howie directly they would not continue working with Josh.

- **Yasmin's team — status-check automation opportunity (new, from 2026-08-06 call):** Howie flagged that Yasmin's team currently has real staff manually checking in with law firms on case status via email — work he explicitly framed as ideal for AI-driven automation ("we have real people doing things that could just be sending emails out and getting AI emails out to lawyers, checking in on them... which is ridiculous"). Distinct from the Julius inactive-account cadence below — this is active-case status-check outreach, not inactive-account re-engagement. Strong candidate for the Opportunity Map deliverable in the 2026-08-06 proposal.

### Salesforce Reports (new, from Howie dictation 2026-07-28)
The CEO reviews these reports daily as part of his morning Salesforce task routine. They are **named reports in Salesforce** but are not explicitly referenced elsewhere in this workflow map:

| Report Name | Purpose | Frequency |
| --- | --- | --- |
| **Prospects** | All active prospects in the pipeline | Daily |
| **Top Prospects** | Highest-value active prospects | Daily |
| **Top Companies** | Top law firms (by revenue/relationship value) | Daily |
| **Inactive Report (Case Financing)** | Accounts inactive for case financing | Monthly (CEO) + ongoing (Julius behind the scenes) |
| **Inactive Report (Pre-Settlement)** | Accounts inactive for pre-settlement financing | Monthly (CEO) + ongoing (Julius behind the scenes) |

These reports are reviewed **daily alongside the task list** to keep the CEO abreast of the full pipeline. Many prospects are already in the CEO's open task list, but these reports surface additional opportunities. Follow-up with contacts at top companies keeps the CEO "in front of them." **This is a named, documented set of reports — not a hypothetical dashboard.** The Sales Performance & Accountability Framework mentions a "shared KPI dashboard" but these are the actual named reports that exist today.

**⚠ Confirmed, broader context (Kaz call, 2026-08-XX): these 5 reports are a small fraction of what exists.** Salesforce holds roughly **100 reports** total, and Howie does not know where to look for most of them — a direct contributor to why an AI-curated digest (see want #19 in [[xx_howies_wants]]) is a stronger fix than building yet another report.

### Salesforce Platform Reference (new, from Kaz call, 2026-08-XX)

**How a lead enters the system — the IPR.** "IPR" is Capital Financing's term for the record created when someone submits the website's financing-interest form (e.g., a plaintiff requesting cash against a pending case). Submitting the IPR creates a record in Salesforce automatically. Separately, and manually, intake **also re-enters the same submission into JB/Mighty** — confirmed double data entry at the point of intake, not simply a one-directional Mighty→Salesforce sync as earlier assumed. One IPR field is a free-text "referring attorney" box the submitter fills in themselves; it's frequently misspelled or informal (first name only, wrong spelling), so a staff member has to manually match it to the correct attorney/firm record before that firm's referral-tracking numbers (last referral date, referral count, amount approved/accepted) update correctly. Every 30 days, active/inactive status per firm is also updated — manually, not automatically.

**Mighty ↔ Salesforce status sync.** Confirmed: Mighty has no API. Whenever an IPR's underwriting stage changes in Mighty (denied, approved, etc.), **someone must manually go into Salesforce and update the corresponding status field to match** — this is the same single Salesforce touchpoint Contracting owns post-underwriting (see Process Trunks systems glossary above), extended here to cover the earlier underwriting-stage changes as well. That status change is what triggers Salesforce's automated drip email sequence to the applicant.

**Drip campaign history and current state.** Roughly **18 different drip campaigns** exist, none highly personalized — described by Kaz as basic status-update messaging ("you've been approved," "we're going to talk to you," "don't stop going to the doctor"), separate from the text messages Contracting sends manually outside Salesforce (see the SOP in `SOPs/`). **Historical note, likely relevant to why the drips Yasmine flagged as "currently paused" are paused:** Capital Financing previously used a *different*, Salesforce-native email-marketing product for this (switched to it to save money and keep everything "native"), but it was badly built — Kaz's example: pasting an image into an email would render blank. Howie stopped paying for it and it was shut off. `[TO CONFIRM: whether the currently-paused drips Yasmine referenced are this same discontinued tool, a different one, or the original pre-switch system — not yet confirmed which.]`

**What counts as "activity."** Outlook calendar integration is confirmed and automatic — any meeting scheduled in Outlook syncs to Salesforce whether or not it's actually attended. Separately, Salesforce's **list email** feature (one send to many contacts at once, fanned out individually in the background) exists and is used by staff, but **Howie does not count a list email as a logged activity** even though the system could log each one. Only a created task, a logged meeting, or a manually-logged individual activity counts as real activity in his own accounting. This is a previously-undocumented, likely significant reason consultant "activity" looks sparse in reports even when genuine bulk outreach is happening — part of the gap may be definitional, not pure non-compliance. Nobody currently logs individual outbound emails one-by-one (confirmed as impractical given normal back-and-forth volume).

**Opportunity tracking — built, not adopted.** See Workflow 4 Core Step 4 for full detail: a full Opportunity object with case-expense/pre-settlement-specific stages, and automated task/notification logic (7-day no-meeting trigger, 30-day no-referral trigger) already exists, built by Kaz and Josh together. It has never been rolled out to the sales team, so it currently has no data flowing through it. This is the single most consequential finding from this call — see want #10 in [[xx_howies_wants]].

**Hunter vs. farmer.** Kaz's own framing for a gap Howie has also independently named: the current financial-consultant team is built of "farmers" (relationship-based closers, good with warm/handed-off leads) rather than "hunters" (cold prospectors who go find new business). Julius was hired specifically to try to fill the hunter gap via automated/semi-automated outreach cadences (see Workflow 3) — so far without producing a single meeting.

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
- **Two-step sequence, confirmed (Howie email, 2026-08-07):** A **Strategy Call** precedes onboarding — set up whenever a law firm expresses interest, run by the FC alone or with Howie if needed, covering Capital Financing's services and the strategy for using them. If the firm wants to move forward with case financing, an **Onboarding Call** is scheduled next — implemented a couple of years ago specifically because results were poor without it. Howie describes the current post-onboarding pattern as: firm leaves the onboarding call genuinely excited, but the first case rarely arrives in week one, and results after onboarding are a persistent struggle — "excuses, not a priority, or confusion." No structured mechanism currently pulls a firm through from "excited on the call" to "actually sends a case."
- **Current follow-up mechanism, confirmed (Howie email, 2026-08-07):** After the onboarding call, Christy or the FC sends a follow-up email with roughly **six attachments** needed to move forward. This is the piece Kaz already built KPI/automation tooling around in Salesforce ("for everybody") — Howie has not yet reviewed with JC and Kaz whether this automation is actually effective or how to improve it. Cross-reference want #13 in [[xx_howies_wants]].
- **⚠ Submission format named as the core friction, confirmed (Howie email, 2026-08-07):** The six-attachment follow-up routes into a **Word document** Christy built for firms to fill out and email back. Howie has told her directly it looks "unappealing, overwhelming, and unprofessional." He wants it replaced with a branded landing page/portal that either feeds Salesforce directly or emails intake for manual entry into Mighty/Salesforce — see want #14 in [[xx_howies_wants]] for the full specification he provided, including a PWA/installable-app layer (want #18) aimed at the deeper problem of firm staff simply forgetting the portal exists weeks after onboarding.
- **Detailed consultant-facing SOP proposed, not yet adopted (Howie's Follow-Up SOP doc, 2026-08-07):** Howie drafted a full five-touch follow-up sequence for consultants to run after every onboarding call (commitment on a specific next-referral date + named day-to-day contact at signoff, then structured touches at Day 1–2, Day 5–7, Day 14, and an ongoing monthly standing check for all active firms). This is a proposed process, not a confirmed current-state practice — needs review with Christy and the FCs before being treated as an actual SOP. See want #15 in [[xx_howies_wants]] for the automation layer built on top of it.

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
- **In:** Approved amount + terms (contract type/fee model selected by whoever approved underwriting — Christy or, currently while she's out, Howie).
- **Out:** Funding agreement generated and sent for signature.
- **Owner/System:** **Contracting trunk** — Yasmin (owner), with Audra, Chanel, Diana / **JB generates the contract as a Word document** based on the selected model; uploaded into **FormStack by Intelistack** for e-signature.
- **Confirmed contract types (Yasmine walkthrough, 2026-08-XX) — decided during underwriting, not by Contracting:**
  - **25% model ("our advertised model," most-used):** 12-month term, 25% fee on principal accruing quarterly (every 90 days), all fees terminate at 12 months.
  - **5% Simple Agreement:** previously ran with no fixed term (ongoing until case settled); changed roughly a week before this call to cap at **48 months**, driven by state-level caps on funding-contract terms that vary by jurisdiction.
  - (See Workflow 2 for the case-expense-specific 15% model.)
- **⚠ Confirmed:** Attorney sign-off on funding is required before approval is finalized — this is the step the CEO's direct file intervention (Core Step 4 breakpoint) has bypassed, with account-loss risk as the explicit concern raised internally.

### Core Step 6 — Agreement Executed
- **In:** Contract sent via FormStack.
- **Out:** Fully signed, executed funding agreement, uploaded back into JB tagged "signed contract."
- **Owner/System:** **Contracting trunk** — Yasmin, with Audra, Chanel, Diana / **FormStack by Intelistack**, using a **single shared login for the whole Contracting group** (not individual per-user logins — a direct, confirmed contrast with what Segue proposed but could not actually demonstrate live during their own demo, since it wasn't connected on their end). Contracting pre-maps a signature-field template per contract-type + funding-method combination (e.g., "25% + ACH direct deposit"), adds signers (client and/or attorney, depending on agreement type), and sends. FormStack auto-reminds signers, and Contracting also manually cross-checks the inbox and sends manual reminders each morning as a double-check against anything the system might have missed.
- **⚠ No defined reminder cadence exists as a written rule** — confirmed as roughly every couple of days in practice, not a documented SLA. If a firm goes fully unresponsive after several follow-ups, the application is closed out in JB (easily reopened later if the firm comes back).

### Core Step 7 — Disbursement
- **In:** Executed agreement; plaintiff payment details.
- **Out:** Funds disbursed; advance recorded against the case; file status moves from **Approved → Funded** in JB, then to **Lien** status.
- **Owner/System:** **Funding trunk** — Danielle, Audra (same two people who staff Contracting) / three payment rails, each with its own threshold:
  - **Push-to-Debit** (via **AppPay**, a separate app from JB) — capped at **$2,500** currently (under discussion with Danielle to raise, since the cap is inconvenient); fastest and most-used method for plaintiffs specifically; requires a photo of the client's debit card for verification (accommodates less computer-savvy or injured clients); never used for law-firm-side payments. If an amount exceeds the cap, it's split across **multiple push-to-debit transactions on different dates**, not switched to another method.
  - **Direct Deposit** — via the company's bank/treasury, requires a voided check or bank letter (name, account, routing); used for both plaintiffs and law-firm reimbursements; no cap, but **per-staff authorization thresholds**: Audra up to $25,000, Chanel (newer) up to $10,000, Yasmine unlimited.
  - **Wire** — restricted to **Yasmine and Danielle only**; nobody else on the team is authorized to send a wire.
  - **Standard practice, all methods:** Contracting always does a phone call with the plaintiff client before releasing funds, to review the terms of the loan/contract with them directly.
- **⚠ Confirmed:** the **funded date and the agreement-signed date are tracked separately** in JB — interest/fee accrual starts on the day funds are actually released, not the day the contract was signed, and these two dates are manually adjusted in JB when a file moves to Funded to reflect what actually happened rather than default field values.
- **⚠** Mighty/JB is static, no API, no Salesforce integration for disbursement data — funding records don't flow to the CRM. **One confirmed exception:** see Core Step 8 note on the single Salesforce touchpoint.

### Core Step 8 — Record-Keeping & Repayment Tracking
- **In:** Funded terms; settlement timeline.
- **Out:** Advance tracked to settlement as a **lien** in JB; repayment recovered at settlement.
- **Owner/System:** **Accounts Receivable trunk** — Jalicia (VA, part-time, 323 files at time of this call), Diana (VA, 313 files), Yasmine herself (261 files), Chanel (also Contracting, 187 files) / JB.
- **Confirmed repayment mechanism:** repayment happens as **one lump sum at case settlement**, and it is the **law firm**, not the plaintiff directly, that pays Capital Financing back from the settlement funds — true even for plaintiff-side pre-settlement advances.
- **Confirmed lien tracking:** each case has one client/case ID in JB; repeat advances against the same case increment a lien/advance number under that same ID (one example cited: a single client with 24 separate advances over time). JB displays current balance and the next scheduled fee-increase date directly on the lien record (quarterly, under the 25% model).
- **⚠ Confirmed: AR follow-up is fully manual, with no automated reminders in JB.** Default follow-up cadence depends on case status (e.g., litigation status defaults to a 90-day interval) but is adjusted per relationship at Yasmine's discretion — established, high-volume, low-risk law firms may get a longer interval (120 days) instead of the default. This is a discretionary practice, not a documented rule. See **Workflow 6** below for the full close-out and payoff process.
- **Confirmed, single Salesforce touchpoint for Contracting:** the only time Contracting touches Salesforce is to flip a record's status to **"Approved"** once JB shows underwriting approval. This used to auto-trigger marketing drip email sequences to the law firm; those drips are currently **paused** (reason `[TO CONFIRM]`). Contracting also manually adds newly-discovered attorney contacts to the firm's Salesforce record so consultants know who's at the firm.

---

# Workflow 2 — Case Expense Financing

**Spine:** `Request → Intake → Underwrite → Agreement → Execute → Pay Vendor → Track`

**Product note:** The growth engine — non-recourse funding for case costs (experts, depositions, medical records); pays vendors directly or reimburses the firm; no guarantee, no credit check; repayable only at settlement.
**Trigger:** A law firm needs case costs funded on an active matter.
**Final deliverable:** Vendor paid (or firm reimbursed) for approved expenses, recorded against the matter and tracked to settlement.

### Core Step 1 — Firm Request Received
- **In:** Firm requests case-expense funding on a matter. `[TO CONFIRM: channel; existing relationship vs. cold referral]`
- **Out:** Case-expense opportunity, entered into JB and **tagged "LIT"** after the client's name — confirmed, this is a manual workaround, since **JB has no dedicated field distinguishing case-expense from pre-settlement**. The same LIT tag is duplicated into the "Capital Providers" field (at 100%) specifically so Contracting can run a report and isolate case-expense volume, since there's no other way to filter for it.
- **Owner/System:** Intake (Rayna et al.) enters it / JB.
- **⚠ Confirmed (2026-06):** This step depends on the firm having been properly onboarded first — see **Shared Sub-Layer — Intake Support, Sub-Step C**. Onboarding quality is inconsistent per-consultant, and a poorly onboarded firm contact produces malformed bulk submissions (e.g., 20 in a day) instead of clean individual requests.

### Core Step 1.5 — Acknowledgement Letter (case-expense specific, confirmed)
- **In:** Underwriting approval.
- **Out:** Signed acknowledgement letter — the law firm gets its own client (the plaintiff) to sign off acknowledging that the firm is taking out funding against their case. Required **before** the funding agreement itself can be sent (see Core Step 4).
- **Owner/System:** Contracting (Chanel or Audra, by law-firm assignment — see Process Trunks notes) reaches out to the attorney/firm directly to request it, logs a note in JB, and follows up roughly every couple of days until it's returned. No automated reminder exists for this step specifically.

### Core Step 2 — Case & Expense Details Collected
- **In:** Case info + specific expenses. `[TO CONFIRM: required fields — matter identity, attorney, expense type(s), vendor(s), amounts, est. settlement value]`
- **Out:** Funding request packet.
- **Owner/System:** Underwriting (Christy, or Howie while she's out) / document collection support per **Shared Sub-Layer — Intake Support, Sub-Step A** where applicable.
- **⚠** Same manual template intake pattern as W1 — confirmed, not just inferred. Case-expense requests are described as frequently "way out of [Tier 1] range," sometimes into the hundreds of thousands — meaning this step usually routes straight to Tier 2 complex underwriting (Christy), bypassing the Rayna/Leifert Tier 1 track entirely.

### Core Step 3 — Underwriting / Approval
- **In:** Case merits; expense schedule; est. settlement value.
- **Out:** Approval + approved amount per expense/vendor + contract model selected.
- **Owner/System:** Christy (Sr. Underwriter), or Howie while she's out — Tier 2 by default given typical case-expense dollar amounts. See **Shared Sub-Layer — Intake Support, Sub-Step B** for the underwriting heuristic (attorney claims are independently vetted, not taken at face value).
- **Confirmed case-expense contract model (Yasmine walkthrough, 2026-08-XX):** **15% fee** (vs. 25% for pre-settlement — Yasmine pushed back on framing this purely as a risk-based difference when asked). An older model charged fees monthly starting from the funding date; that model has been **discontinued**. The current model charges the **first three months' fees upfront/automatically** at funding, then continues from there — exact mechanics past month three still `[TO CONFIRM]`.
- **⚠** `[TO CONFIRM: formal authority thresholds]` — PO-001 risk is more acute here than in W1, since case-expense amounts skew complex/high-dollar and stay with Christy rather than being distributable to Rayna/Leifert.

### Core Step 4 — Funding Agreement Issued
- **In:** Approved terms (non-recourse, repayable at settlement); signed acknowledgement letter (Core Step 1.5).
- **Out:** Case-expense agreement generated by JB, sent to firm via FormStack.
- **Owner/System:** **Contracting trunk** — Yasmin (owner), with Audra, Chanel, Diana / JB generates the Word-doc contract → **FormStack by Intelistack** (shared group login — see W1 Step 6 for full detail on this system).

### Core Step 5 — Agreement Executed
- **In:** Signed agreement returned from firm.
- **Out:** Executed agreement authorizing disbursement, uploaded back into JB.
- **Owner/System:** **Contracting trunk** — Yasmin, with Audra, Chanel, Diana / FormStack → JB, same process as W1 Step 6.

### Core Step 6 — Vendor Payment / Firm Reimbursement
- **In:** Executed agreement; vendor invoices / firm expense docs. `[TO CONFIRM: how invoices are received and verified]`
- **Out:** Payment to vendor directly, or reimbursement to firm — confirmed **always via direct deposit or check into the firm's operating account**, never push-to-debit (push-to-debit has never been used for a law-firm-side payment).
- **Owner/System:** **Funding trunk** — Danielle, Audra / bank/treasury direct deposit, subject to the same per-staff thresholds as W1 Step 7 (Audra $25K, Chanel $10K, Yasmine unlimited; wires restricted to Yasmine and Danielle only).
- **⚠** Mighty/JB isolation — no automated flow of payment data to CRM or firm-relationship records.

### Core Step 7 — Record-Keeping & Repayment Tracking
- **In:** Funded expense amounts; settlement timeline.
- **Out:** Expenses tracked to settlement as a lien in JB; repayment recovered at settlement.
- **Owner/System:** **Accounts Receivable trunk** — Jalicia, Diana, Chanel, Yasmine / JB. Same mechanics as W1 Step 8: lump-sum repayment from the law firm at settlement, manual AR follow-up on a status-based (and relationship-adjusted) cadence, no automated reminders. See **Workflow 6** for the full close-out and payoff process.

---

# Workflow 3 — Outbound Email & Social Cadence

**Spine:** `Source List → Prepare → Send → Handle Replies → Thank-Yous → Social`

**Operator note:** Julius (offshore contractor, $2,500/mo). **Reconciliation resolved (Howie's daily Julius reports, 2026-08-XX):** Howie's "manual sending" account and Kaz's "Salesforce Cadence" account describe the same system — Julius manually triggers/runs sends through Salesforce cadences, so both are accurate at different levels of description. **Confirmed cadence names:** Pre-Settlement Introduction, Case Expense Introduction, Inactive Emails (60-day), and Thank You for the Referral — refining the earlier "3 pre-settlement + 3 case-financing templates" estimate. **Concrete response data, one day (Howie's EOD report, 2026-08-XX):** 101 emails sent to Case Expense Prospects (2nd touch) produced 6 out-of-office auto-replies and 10 hard bounces — **zero substantive replies.** 59 emails sent to Inactive Prospects (60-day) produced 6 out-of-office auto-replies — again **zero substantive replies.** This is the most concrete evidence yet for "near-zero response": not an impression, an actual one-day count showing 160 emails sent, 0 real replies. **Flagged to collapse/reposition once Salesforce automation lands** — map now as transitional.

**New activity, not previously mapped — LinkedIn network growth (Howie's daily reports, 2026-08-XX):** Julius also reviews content (videos, testimonials, PDFs, blogs) for potential social posts, creates infographics/captions for approval, and — not previously documented — **builds LinkedIn connections sourced from Howie's own personal LinkedIn network**, then sends invitations from the Capital Financing LinkedIn Company Page (confirmed volume: 20 invitations sent in one day) to grow the company page's following. This is a distinct activity from Core Step 6 (Social Media Posting) below — it's audience-building rather than content publishing.

**Howie's own reaction to these reports, worth noting directly:** Howie receives an End-of-Day and a Start-of-Day report from Julius every business day, and said of them: "It's a lot, similar stuff, and although great I just don't pay attention." This is a smaller-scale version of the same reporting-glut problem documented in the Salesforce Platform Reference section below (~100 reports, doesn't know where to look) — direct, first-hand evidence *for* want #19's AI-digest approach (a short synthesized summary Howie would actually read, replacing verbose twice-daily reports he currently skips) rather than more raw reporting.
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

### Core Step 7 — LinkedIn Network Growth (new, from Howie's daily Julius reports, 2026-08-XX)
- **In:** Howie's personal LinkedIn connections.
- **Out:** Connection invitations sent from the Capital Financing LinkedIn Company Page.
- **Owner/System:** Julius / LinkedIn (personal profile browsing) + Company Page.
- **⚠** `[TO CONFIRM: conversion — does growing the company page's follower count translate to any measurable business outcome, or is it a vanity metric currently uncounted like the rest of this workflow?]`

---

# Workflow 4 — Sales Consultant Lead Handling

**Spine:** `Lead In → Assign → Follow-Up → Progress → Log → Close`

**Context:** CEO is #1 salesperson + default sales manager; hands warm leads to consultants. Team under-follows-up and under-converts; consultants resist CRM notes; sales side unmanaged.
**Trigger:** A warm lead exists (CEO, conference, referral, or inbound) to be assigned.
**Final deliverable:** A worked lead with its outcome (converted / in-pipeline / dead) logged in Salesforce.

### Core Step 1 — Lead Generated
- **In:** New warm lead. Sources confirmed (Kaz call, 2026-08-XX): the primary structured source is the **IPR** — a plaintiff or firm submits Capital Financing's website form, which creates a record in Salesforce. Conference contacts and outbound replies are the other main sources.
- **Out:** Lead/contact exists in Salesforce, created automatically from the IPR web form (not manual entry for this specific path).
- **Owner/System:** Website form → Salesforce, automatic. Intake also **manually re-enters the same submission into JB/Mighty** — confirmed double-entry, not just a one-way Mighty-to-Salesforce sync as previously assumed.
- **⚠ Confirmed data-quality issue:** the IPR's "referring attorney" field is free text filled in by the plaintiff/submitter, and is frequently misspelled or informal (e.g., first name only) — a staff member has to manually match it to the correct attorney/firm record before referral tracking (last-referral date, referral count, amount approved) can update correctly for that firm.

### Core Step 2 — Lead Assigned to Consultant
- **In:** Lead + assignment logic.
- **Out:** Lead owned by a named consultant (Audrey, Victoria, Brian, Lisa…).
- **Owner/System:** CEO (default sales manager) / Salesforce. **Confirmed conference-contact assignment process (Kaz call, 2026-08-XX):** every new contact from a conference list defaults to being owned by Howie first. After the list is imported (see Workflow 5, Core Step 4), Howie manually redistributes by percentage per consultant (e.g., "25% to this person, 20% to this person, none to that person") — there is no criteria-based routing logic, and once reassigned, there is **no tracking of what happens next**; consultants receive the batch with no visibility into whether they're worked.
- **⚠** Assignment is CEO-driven and manual; no managed routing layer.

### Core Step 3 — Consultant Follow-Up
- **In:** Assigned lead; segmented list (e.g., post-conference).
- **Out:** Follow-up attempts (calls/emails).
- **Owner/System:** Consultant / Salesforce, syncing automatically with Outlook — **confirmed (Kaz call, 2026-08-XX):** any calendar invite/meeting scheduled in Outlook automatically appears in Salesforce, whether or not the meeting is actually attended.
- **⚠** Consultants not following up on segmented lists; no activity minimums, no reporting cadence, no pipeline ownership.
- **⚠ Post-onboarding 1-week referral tracking (new, from Howie dictation 2026-07-28):** After onboarding, Capital Financing requests the law firm send their first referral within **one week**. Most firms do not send cases within that window — sometimes not for months. This is why the task system exists: to catch them proactively. The CEO's daily Salesforce routine explicitly checks whether post-onboarding firms have sent their first referral. This cadence (1-week target, multi-month reality) should be the standard follow-up cadence for post-onboarding accounts, but currently no cadence is defined or enforced for consultants.
- **⚠ Confirmed (2026-06):** Case-expense onboarding calls specifically — a Workflow 4/Shared-Layer crossover point — are weak: "our sales team... they're awful at having these calls." This is a named, confirmed skill gap, not just a process gap. See **Shared Sub-Layer — Intake Support, Sub-Step C**.

### Core Step 4 — Pipeline Progression
- **In:** Prospect responses; qualification.
- **Out:** Opportunity advanced through stages.
- **Owner/System:** Consultant / Salesforce.
- **⚠⚠ Major finding, confirmed (Kaz call, 2026-08-XX): a defined Opportunity object with stages already exists and is fully built — it is simply not being used.** Kaz and Josh built an Opportunity structure with stages that differ by product (case-expense vs. pre-settlement), plus automated logic on top: if two required meetings haven't happened within 7 days of an opportunity's creation, a follow-up task auto-generates; if no referral arrives within 30 days of the second meeting, a notification fires. **Nobody currently creates Opportunities**, so none of this automation has data to act on. This resolves the prior `[TO CONFIRM]` on whether defined stages exist — they do, they're just unused. See want #10 in [[xx_howies_wants]] for the reframed priority: this is now an adoption/enforcement problem, not a build problem.

### Core Step 5 — CRM Logging & Task Lifecycle Management
- **In:** Activity + outcome data.
- **Out:** Notes, activities, status recorded in Salesforce.
- **Owner/System:** Consultant / Salesforce.
- **⚠** Consultants resist notes; logging inconsistent (no standard ties to what's recorded); reports built but never opened.
- **⚠ Confirmed activity-tracking definition (Kaz call, 2026-08-XX):** Howie does **not** count a Salesforce "list email" (a bulk send to many contacts at once) as a logged activity, even though the system technically sends and could log each one individually. Only a created task, a logged meeting, or a manually-logged individual activity counts toward what Howie considers real activity. This is a meaningful, previously-undocumented reason consultant "activity" looks sparse in reports even when bulk outreach is genuinely happening — the gap may be partly a definitional mismatch, not pure non-compliance.
- **⚠ Task lifecycle management (new, from Howie dictation 2026-07-28):** The CEO's daily routine includes a full task lifecycle: create task with due date (2 weeks to 1 month out, based on urgency) → check off when completed → create a *new* task for the next follow-up → **remove** tasks for firms that are no longer useful (don't let them sit as "zombie tasks"). This lifecycle (create → schedule → complete → remove) is not currently part of any consultant workflow or SOP. Currently there is no mechanism to remove unproductive tasks — they just accumulate. This should be a standard practice for all consultants: if a task is determined to be no longer useful, remove it rather than letting it sit indefinitely.

### Core Step 6 — Outcome / Close
- **In:** Final disposition.
- **Out:** Lead marked converted (→ funding W1/W2), in-pipeline, or dead.
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
- **Out:** Raw list of new contacts — Howie sends Kaz a **pre-conference list** and a **post-conference list**.
- **Owner/System:** CEO / team capture in person; Howie compiles and sends to Kaz / `[TO CONFIRM: capture method at the event itself]`
- **⚠** `[TO CONFIRM: how raw contacts reach Salesforce — manual entry, bulk import, or not at all]` — partially resolved by Core Step 4 below.

### Core Step 4 — Contact Loading & Segmentation
- **In:** Raw event contacts (pre- and post-conference lists from Howie).
- **Out:** Contacts loaded into Salesforce, deduplicated against existing records (segmentation + list-email capability exist in build).
- **Owner/System:** **Kaz** — confirmed (2026-08-XX call), resolving the prior `[TO CONFIRM: CEO, Kaz, or consultant]` — / Salesforce, via manual spreadsheet work plus some AI-assisted lookups.
- **⚠ Confirmed, previously invisible cost:** Salesforce holds roughly **25,000 contacts and 10,000 companies**. Matching a new conference list against existing records is manual — name/spelling inconsistencies (dashes, nicknames vs. legal names, slightly different firm names, manually-entered vs. self-registered spellings) mean only about **50% auto-match**; the rest requires Kaz to manually reconcile duplicates by hand. This takes roughly **2 hours per list**, every time Howie sends one — a real, recurring cost that wasn't previously counted anywhere. See want #8 in [[xx_howies_wants]] for the automation angle on this.

### Core Step 5 — Assignment & Follow-Up
- **In:** Segmented post-conference list.
- **Out:** Lists assigned to consultants → feeds Workflow 4.
- **Owner/System:** CEO → consultants / Salesforce.
- **⚠ Confirmed assignment mechanism (Kaz call, 2026-08-XX):** every new conference contact defaults to being owned by **Howie** once loaded (Core Step 4). Howie then manually redistributes by rough percentage per consultant ("25% to this person, 20% to this person, none to that person") — there is no criteria-based routing, and **no tracking exists of what happens to a contact after reassignment**. This is the same mechanism documented in Workflow 4 Core Step 2.
- **⚠** Primary documented failure point: consultants don't follow up, so the ~$20K spend doesn't convert.

---

# Overall Workflow (Placeholder — to be strung together)

Once each spine above is on the canvas, the **Overall** flow links them end-to-end. The likely connective seams (all `[TO CONFIRM]` unless noted):

`W5 Conference → W4 Sales Handling` — segmented event lists feed consultant follow-up (W5 Step 5 → W4 Step 1).
`W3 Outbound → W4 Sales Handling` — interested replies should become tracked leads (W3 Step 4 → W4 Step 1). ⚠ link not confirmed today.
`W4 Sales Handling → Shared Sub-Layer Sub-Step C → W2 Funding` — **confirmed seam for case expense:** a closed firm relationship (W4 Step 6) leads to firm onboarding (Sub-Step C), and onboarding quality directly determines whether the firm's first W2 submission is clean or malformed.
`W4 Sales Handling → W1 Funding` — the pre-settlement equivalent bridge remains **undocumented** — the single most important seam still to define for the plaintiff side.
`W1 / W2 → (loop back)` — funded relationships feed referral thank-yous and repeat case-expense requests, reinforcing the stickier firm relationships.

`Salesforce Daily Routine → All W1–W5` — The CEO's 8-step daily routine (see **Salesforce Daily Routine** in Overall Workflow above) is the overarching governance layer that touches all workflows. It is the daily operating rhythm that ensures nothing falls through the cracks — but currently only the CEO performs it. Whether consultants are expected to perform an equivalent daily routine (or whether automation replaces the need for one) is a key design question for ranked want #10 (`xx_howies_wants.md`).

> Build note: the Overall spine is **not** a sixth workflow to map from scratch — it's the join of the five existing spines (plus the Shared Sub-Layer) at these seams. Confirm each seam's actual hand-off mechanism before drawing the connectors.

**Salesforce Daily Routine (Sales Leadership — new, from Howie dictation 2026-07-28; extended 2026-08-05)):** The CEO performs a 10-step daily routine in Salesforce (documented in full at `SOPs/20260728_Capital-Financing_Daily-Salesforce-Task-Review.md`). This is not a workflow spine — it is an **overarching governance layer** that touches all workflows daily:

0. Plan the day/week in advance — review calendar the night before or early morning, set an alarm for every meeting, target at least 4 meetings booked/day (2026-08-05)
1. Start Salesforce → review current/overdue tasks
2. Open each task → review subject, related contact, all notes
3. Reach out (email/phone/both) to contact
4. Determine follow-up reason (post-strategy call vs. post-onboarding)
5. Use task bar for conference follow-ups
6. Check off completed tasks → create new task with due date (2 weeks to 1 month out, based on urgency)
7. Review Top Companies / Top Prospects reports
8. Monthly: review inactive reports (case financing + pre-settlement)
9. Fill any unbooked time with inactive-account outreach, prior-conference reporting, and general prospecting/pipeline-building (2026-08-05)

This routine touches **W4 (consultant follow-up)** and **W5 (conference follow-ups)** directly. It also surfaces the 1-week post-onboarding referral tracking gap (see W4 Step 3). The CEO's routine should be documented as a governance layer that sits above and touches all five workflow spines — it is the daily operating rhythm that ensures nothing falls through the cracks.

**Post-funding tail not yet mapped as spines.** Christy's trunk roster surfaces two operational functions that sit *after* W1 Step 8 / W2 Step 7 and are not yet drawn as workflow spines:
- **Payoffs** (Diana, Jalicia, Audra, Chanel, Yasmin) — resolving repayment at settlement.
- **Collections** (Yasmin) — recovering overdue/at-risk repayments.

These likely warrant their own spine — call it **Workflow 6 — Repayment / Payoffs / Collections** — now mapped below following Yasmine's detailed walkthrough (2026-08-XX).

---

# Workflow 6 — Post-Funding: AR, Payoffs & Close-Out (Yasmine's team)

**Spine:** `AR Tracking → Payoff/Reduction Request → Deposit Received → Reconciled → Closed`

**Trigger:** A funded case (from W1 or W2) sits as a lien in JB, awaiting settlement.
**Final deliverable:** Case repaid, deposit reconciled against QuickBooks, file closed out in both JB and QuickBooks, and — if relevant — logged as closed in Funding Exchange.

### Core Step 1 — AR Tracking (ongoing, manual)
- **In:** Funded lien; case status.
- **Out:** Periodic law-firm touch confirming case status, until settlement.
- **Owner/System:** Jalicia, Diana, Yasmine, Chanel (see per-person file counts in W1 Step 8) / JB — fully manual, no automated reminders exist.
- **⚠** Cadence is status-based (e.g., 90 days for litigation) and discretionary per firm relationship (VIP/high-volume firms may get 120 days) — not a documented rule. This is the same status-check outreach Howie flagged as an automation candidate in the 2026-08-06 kickoff call (see Process Trunks notes and want #15 in [[xx_howies_wants]]).
- **Cross-funder check (Funding Exchange):** Before underwriting, intake already ran a check in the external **Funding Exchange** platform (client name, DOB, last-4 SSN) to confirm no other funding company already has a lien on the case — since whichever funder advanced first gets repaid first if settlement proceeds run short. Once this case funded, Contracting logged the new lien into Funding Exchange as well, so other funding companies can see it.

### Core Step 2 — Payoff or Reduction Request Received
- **In:** Inbound request to a dedicated **payoff email inbox** — either a standard current-payoff-balance request, or a reduction request (firm asking Capital Financing to accept less than the full balance).
- **Out:** Routed by request type.
- **Owner/System:** Yasmine (payoff department) / dedicated shared payoff inbox.
- **Standard payoff:** Yasmine or team pulls the current balance/lien detail directly from JB, generates a payoff confirmation letter (JB-generated template), and sends it along with the signed agreement — CC'ing Contracting and the client.
- **Reduction request:** routed to **Howie for approval or denial** before any reduced-payoff letter is generated or sent — this is the one payoff-side decision that isn't Yasmine's to make alone.

### Core Step 3 — Deposit Received
- **In:** Settlement check(s) arrive.
- **Out:** Deposit logged.
- **Owner/System:** Intake-side VA (deposits) tags Howie and Danielle, then assigns the file to Yasmine, noting the check number(s) and deposit date. No follow-up date is set at this point since it's awaiting bank clearing, not a chase.

### Core Step 4 — Reconciliation
- **In:** Cleared deposit (next business day after Step 3).
- **Out:** Deposit confirmed matching the expected bank amount.
- **Owner/System:** Yasmine / JB cross-checked against QuickBooks. Once confirmed, she assigns the file to Danielle for close-out.

### Core Step 5 — Close-Out
- **In:** Reconciled, matched deposit.
- **Out:** File closed in both systems.
- **Owner/System:** Danielle / JB + QuickBooks. Danielle marks the file closed in JB, noting **how** it closed (attorney paid it, client paid it directly — which does happen occasionally — or another funding company bought the lien out, in which case that company's name is logged), and closes it out in QuickBooks.

---

# Cross-Workflow Observations — Organizational Context

These are not workflow steps. They're governance and management dynamics, confirmed via the 2026-06 ops call, that materially affect *how* the workflows above actually execute day to day. Recorded here because they explain several of the breakpoints already noted in the workflow steps, but they are not themselves automatable process — they're a management/authority layer the AI & automation plan needs to account for, not solve directly.

1. **CEO direct intervention in live underwriting files.** Confirmed, recurring pattern (Christy: "he does this... every single time"): the CEO bypasses the underwriting and attorney-approval steps by entering files directly and attempting to approve funding before the attorney of record has signed off. This creates account-loss risk (attorneys may fire Capital Financing over unauthorized approvals), generates emotional/rework fallout across the team, and undermines the very underwriting structure (tiering, heuristic) documented in the Shared Sub-Layer above. This is the direct cause of the Core Step 4/5 breakpoint flagged in Workflow 1.

2. **Volume is undercounted at the leadership level.** The CEO's volume metric tracks *approved* funding only. Christy's actual workload includes total *inbound* volume — emails, voicemails, calls, partial/incorrect submissions, and the rework loop from poorly onboarded firms — which is materially higher and growing into the firm's busy season. This mismatch is the root cause of recurring staffing disputes (see #3) and likely understates true operating load across Workflows 1, 2, and the Shared Sub-Layer.

3. **Contested authority over intake/underwriting staffing decisions.** A recurring pattern, per Christy, of the CEO proposing a new hire (most recently Tammy) as a wholesale replacement for an existing staffing plan (the two VAs, and the Rayna/Leifert Tier 1 underwriting growth path) rather than as additive capacity — then reversing or denying prior commitments when challenged (e.g., disputing that Tier 1 underwriting training for Rayna/Leifert had ever been promised, twice). Christy frames this as a recurring pattern across multiple past hires, not a one-off. Net effect: staffing plans for the Shared Sub-Layer are unstable and subject to reversal outside the documented growth/tiering structure.

4. **Unclear management authority outside the CEO/Christy reporting line.** A separate department (Yasmin's team, which includes contracting) operates partly outside Christy's ability to manage directly — attempts to manage Yasmin in the past resulted in informal escalation to Danielle (part-owner) and friction that affected Christy's working relationship with the CEO's circle. Danielle has independently made management decisions affecting Yasmin's team (e.g., promoting a team member to manager with an office) without consulting Christy or, per the call, without a clear documented process behind the decision. This is relevant context for any automation work that touches contracting or Yasmin's department, since the actual decision-making authority there is not where the org chart would suggest.
   - **Corroborating evidence, a different angle (Howie's inbox self-scoping email, 2026-08-XX):** Howie independently named the same underlying pattern from his own side of the inbox — staff/HR/controller questions come to him instead of Christy, and financial consultants loop him in on things Christy should own as underwriter, purely out of habit or a preference for dealing with the CEO directly. His own words: this "undercuts Christy's role." This is the same authority-vacuum dynamic as the Yasmin/Danielle case above, playing out through email habits rather than formal management decisions — worth treating as one pattern (Christy's DOO authority isn't consistently respected company-wide), not two separate issues, when scoping any fix.

5. **Net effect on the automation plan.** None of the above are workflow inefficiencies that automation fixes directly — they're authority and communication patterns that will determine whether any process change (tiering, onboarding scripts, CRM discipline, etc.) actually sticks once implemented. Worth surfacing explicitly in the opportunity map as a "process governance" risk alongside the technical opportunities, since a clean automated workflow can still be broken by ad hoc file intervention or reversed staffing decisions.

6. **New institutional knowledge infrastructure.** CEO is implementing SharePoint as "institutional knowledge bank" for all processes and documentation. All team members are being trained on SharePoint structure and usage, with enforcement to come. Clear benefit: distributed knowledge capture reduces tribal knowledge dependency on individual staffers (e.g., Christy's free-form Mighty approach). Risk: SharePoint adoption has historically been weak at Capital Financing ("It's not very user-friendly... staff can't find it"), so training and ongoing discipline will be critical to success. This is the first layer of a broader accountability framework (see #7).

7. **New accountability and measurement framework rolling out.** CEO is formalizing KPIs, goals, and performance metrics for all roles (currently mostly absent). Monthly one-on-one reviews by CEO with each team member will become the enforcement mechanism. Tone is results-focused and non-negotiable: missing goals leads to performance management conversation; repeated non-compliance leads to termination. This is a material shift from the current state and will directly affect workflow compliance. Example: sales team follow-up (W4/W5) is currently weak because accountability is loose; new measurement layer will make follow-up discipline a tracked metric with consequences. Early warning: this may surface additional breakpoints as workflows are measured rigorously for the first time.
- **New: Salesforce daily routine as accountability mechanism (from Howie dictation 2026-07-28):** The CEO's 8-step daily Salesforce task review is itself an accountability mechanism — he reviews current/overdue tasks, contacts people, checks off tasks, creates new tasks with due dates, and reviews reports. The question is whether this accountability layer should be extended to consultants (manual) or replaced by automation (ranked want #10). See `SOPs/20260728_Capital-Financing_Daily-Salesforce-Task-Review.md`.

8. **Post-Josh transition — reprioritization and new working model (2026-08-06 call).** Howie independently confirmed, in his own words, that operations was not where this engagement's help was most needed ("we don't have a lot of issues operationally... Christy and her leadership team are doing great") — sales productivity and tech/automation efficiency are the actual priority, validating PO-005 over the operational/COO-style work Josh focused on. Howie also self-attributed part of the operational gap to his own lack of delegation — Christy holds the DOO title but was never clearly directed to lead SOP/workflow rollout ("I blame myself"). Going forward, JC works primarily through Christy for team dissemination rather than managing departments directly, and individual reset conversations with Christy, Danielle, and Yasmin are planned before further work, specifically to establish a different working relationship than the one the team had with Josh. See [[xx_Project_Learnings]] for full call detail and `client-facing-deliverables/20260806_proposal-capital-financing-ai-automation-mapping.md` for the resulting scoped proposal.

---

# Sales Performance & Accountability Framework (CEO Directive)

Based on CEO strategic conversation (2026-06), a new accountability and measurement layer is being implemented across the sales team. This is a **management context** that will materially affect how Workflows 3, 4, and 5 (Outbound, Sales Handling, Conferences) are tracked and executed going forward.

## Sales Team Current State & Expectations

**Audrey** — Sales Consultant, ~3.5 years tenure
- **Performance:** $1M+ in business generated; should be $2M
- **Volume:** 12–15 plaintiff loans/month; target is 50/month
- **Issue:** Despite conference attendance and lead lists, follow-up is inconsistent (CEO caught her not following up with recent prospect, "Parrish")
- **Conflict of interest:** Side business in diminished-value consulting; gives business cards at Capital Financing–funded conferences, creating confusion about whose business she's promoting
- **CEO directive:** Establish clear guardrails on side business; do open-ended diagnostics on barriers to higher production; improve follow-up discipline
- **Accountability measure:** Track number of law-firm relationships (should grow from current baseline), number of outreach attempts per month, follow-up closure rate per lead source
- **Guardrail framework:** Side business permitted *only if* it does not bleed into Capital Financing territory or time; first violation = termination

**Brian** — Sales Consultant, new hire (brand new, ~1 month tenure)
- **Performance:** Great potential; good communicator; strong lead generation (returned from conference with significant leads)
- **Issue:** Over-focused on case expense (7x lower volume than pre-settlement), poor professional judgment (appeared on video call with prospect wearing baseball cap)
- **CEO directive:** Refocus on balanced portfolio (pre-settlement and case expense equally important); implement structured tracking and accountability guardrails; professional conduct expectations
- **Accountability measure:** Track case-expense vs. pre-settlement lead ratio (should be 1:7 to match CEO's business split); opportunity conversion rate; pass-through execution rate (if CEO passes him opportunity, measure whether he executes)
- **Framework:** Early-stage coaching on professional judgment; escalate non-compliance to CEO immediately
- **Update (Transcript 1, 2026-08-06 end-of-month call):** Confirmed not using Salesforce reporting functionality despite being trained on it (has the training videos, hasn't watched/applied them). Doing things "his own way" instead — missing out on the reporting and automation already built. Howie says he's seeing this **across the board with all consultants**, not just Brian. Also showed up to this call with his commissions-tracking spreadsheet incomplete; Howie spent 30 minutes walking him through fields live — see the new commissions-spreadsheet want (#7 in `xx_howies_wants.md`) and PO-002/PO-004 addenda in the discovery brief. Howie gives Brian grace as a new hire, but reads this as a broader onboarding/training gap, not just a Brian issue.

**Victoria** — Sales Consultant, 3+ years tenure
- **Performance:** ~$250K/year in business; no account growth; geographically constrained (South Florida only, except 2 accounts)
- **Issue:** Lacks motivation and accountability; serial non-compliance (missed commission submissions 4–6 months at a time); ignores direction ("yesses to death, then doesn't do it"); no drive to expand geographically despite repeated requests; posts gym photos on social media daily but makes no outreach effort
- **CEO directive:** Set immediate, hard expectations; first non-compliance = termination or conversion to independent contractor status
- **Accountability measure:** Commission submission deadline compliance (weekly, mandatory); geographic expansion metrics (trips booked, new-market prospect list); activity logs (calls, meetings)
- **Current status:** On commission-only pay (no salary); no longer has salary leverage; CEO considering removing company credit card and making her true 1099 independent contractor

**New Performance Measurement Layer — All Sales**
- **Corrected 2026-08-06:** the shared KPI dashboard is not merely "being implemented" — Kaz already **built** it to Howie's spec roughly mid-to-late June 2026. Howie reviewed it once, asked for fixes, Kaz fixed it, and then Josh took ownership of it roughly three weeks before his departure. It has not been rolled out to the team since, and Howie had assumed it was handled ("we met with Josh, we met with Kaz, saw what he did... this was easy") until checking in and finding nothing had moved. The gap is rollout and adoption, not the build itself — this is a strong candidate to be one of the 1–2 quick wins in the 2026-08-06 proposal rather than new work.
- Expected outputs: law-firm relationship growth (volume), outreach attempt counts, follow-up closure rates, conference lead quality, product-line balance (pre-settlement vs. case expense)
- **Accountability mechanism:** CEO conducting monthly one-on-one calls with each sales consultant to review performance against expectations
- **Confirmed breakpoint (Transcript 1, 2026-08-06):** consultants are expected to arrive at these monthly calls with a commissions-tracking spreadsheet fully filled out. They routinely show up unprepared — Howie has told the team directly not to do this ("it's a waste of my time") but it keeps happening, and calls end up burning time on data entry that should have been done in advance. See ranked want #7 (`xx_howies_wants.md`) for the automation angle on this.
- **Non-negotiables:** Goals will be documented and communicated; missing goals = performance management conversation; repeated non-compliance = termination
- **Tone:** Results-focused; CEO is "all about results" and "all about volume"; flexibility on how/when work is done as long as metrics are hit; no patience for excuses

**Consultant Prospecting Strategy — Whale-Hunting vs. Volume (new, from Howie dictation 2026-08-05)**
- CEO directive for consultants: invest time in constructive, high-value targets rather than spreading effort thin. Explicit framing: "Why would you want to manage 75 law firms when you can manage 25 big companies?" The objective is to prioritize larger law firms with bigger settlements over a high count of small firms.
- Suggested research channels: LinkedIn, general internet/website research, and potentially AI-assisted scoping — using AI to search the internet for law firms that fit the target profile (e.g., firms known for larger settlements) as a starting filter for who to approach.
- Not yet a formal SOP or tool — currently a directive/philosophy communicated to consultants, not a built process. Candidate for a future prospecting SOP or AI-assisted research workflow.

**Consultant Authority & Client Routing (new, from Howie dictation 2026-08-05)**
- CEO has identified a broader, company-wide version of a pattern already noted for Audrey below: clients and prospects — including new ones CEO hands off — continue to reach out to the CEO directly instead of their assigned financial consultant, even after the account has been transitioned.
- CEO's own diagnosis: when a consultant comes across as knowledgeable, authoritative, and communicates clearly about who the client should contact, clients go to that consultant instead of the CEO. Clients bypassing a consultant is read as a signal that the consultant hasn't established a strong relationship or trust with that account.
- CEO explicitly wants advice on whether this is a training issue (some training has already been done) or needs a different operational fix, and wants standard operating procedures/workflows that both build consultants' communication skills and set clear expectations with law firms about who to contact.
- CEO's stated goal: he should not need to be managing accounts that belong to a financial consultant. This directly ties to his broader IOV goal of stepping out of day-to-day sales management (see discovery brief).
- Logged as a new diagnostic item — see PO-007 in the discovery brief's Diagnostic Register.
- **Confirmed (2026-08-06 email):** The stalled Friday sales-team meeting (see Engagement Continuity in the discovery brief) was specifically Josh's planned recurring weekly call with financial consultants/BDRs — intended to build accountability and traction, and directly tied to a "shift client communications from CEO to financial consultants" note. In other words, this recurring call was meant to be the operational mechanism for fixing PO-007. It never launched before Josh's departure. JC plans to eventually meet the FCs to understand how they interface with the rest of the team, but not immediately.

## Staffing Decisions & Their Workflow Impact

- **Lisa** (sales consultant) — terminated after 2 months; departure imminent
- **Victoria** — flagged for immediate performance improvement plan or separation; likely to affect W4 and W5 output/follow-up rates in short term
- **Brian** — growth track, but early; execution tracking will be critical
- **Audrey** — retention goal; need to unlock higher production without losing her to side business
- CEO notes: "I need more Brians" — better salespeople with balanced focus and execution discipline are the stated hiring priority

## Workflow Impact

These sales performance dynamics directly affect:
- **W3 (Outbound Email & Cadence)** — someone must own consistency of send/response/thank-you cycle; currently may be dropping due to consultant overload or unclear accountability
- **W4 (Sales Consultant Lead Handling)** — major documented breakpoint: leads generated but not followed up (Victoria); assignments made but not executed (Brian's passed opportunities); relationship ownership unclear when house accounts call CEO instead of assigned consultant (Audrey's accounts) — **now confirmed as a company-wide pattern, not just Audrey's, per 2026-08-05 dictation; see PO-007 in the discovery brief and "Consultant Authority & Client Routing" above.**
- **W5 (Conference Marketing)** — high spend (~$20K per event), low conversion; follows into W4 (lead assignment) where follow-up discipline is lowest

**KPI focus: financial consultants first (2026-08-06 kickoff call).** Christy recommended prioritizing KPI/automation work on the financial consultants specifically — there's already substantial data on them (from what was given to Josh), and it represents the clearest, fastest win; her own departments (with Yasmine) have comparatively less KPI need at this stage. Howie agreed KPIs are the top priority specifically for the sales team, but corrected that SOPs and workflow documentation still matter across the whole organization, and that Christy needs to be intimately involved as DOO across all departments, not just sales. Net effect: want #10 (`xx_howies_wants.md`, Salesforce follow-up automation & KPIs, FC-focused) is confirmed by both Howie and Christy as the highest-priority automation target for this engagement.

---

# `[TO CONFIRM]` Checklist — Next Discovery Pass

Grouped for an efficient interview (Christy for underwriting/finance; Kaz for CRM mechanics).

**Funding intake & underwriting (W1, W2)**
- Exact required intake fields (plaintiff + case-expense) — partially confirmed; format (CRM vs. email-only) still open
- How supporting docs are chased when a firm is slow to respond
- When a Salesforce record is created vs. email-only
- Formal Tier 1 vs. Tier 2 approval authority thresholds (heuristic confirmed; thresholds not)
- Disbursement mechanics and system of record in Mighty/Justice Bolt (Funding trunk owners now known: Danielle, Audra)
- How settlement status and repayment are monitored (AR trunk owners now known: Jalicia, Diana, Chanel)
- **New ask from Howie (2026-08-06 kickoff call):** Christy and Yasmine need to document intake from the very first point of contact — how something comes in (website, email, call), and every step taken in Salesforce to acknowledge and process it — in more granular detail than currently captured. This level of detail is what automation logic actually needs (touch points, who things get sent to, when, and why).

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
- **Current activity expectations (partially answered):** CEO's daily routine includes a full task lifecycle (create → schedule → complete → remove), 1-week post-onboarding referral tracking target, and daily review of 5 named Salesforce reports (Prospects, Top Prospects, Top Companies, Inactive Case Financing, Inactive Pre-Settlement). However, these are CEO-level standards — the question remains whether they are enforced on consultants, not just the CEO. See `SOPs/20260728_Capital-Financing_Daily-Salesforce-Task-Review.md`.
- Conference contact capture method and import path to Salesforce

**Overall seams**
- The hand-off from closed sales lead → pre-settlement funding intake (W4 → W1) — still undocumented
- Whether outbound replies (W3) connect to the CRM lead flow (W4)

**Sales performance & accountability (new layer, CEO directive)**
- Exact KPIs for each sales role (Audrey, Brian, Victoria) — partially defined by CEO; need formalized dashboard
- **Law-firm relationship growth baseline and growth targets (partially answered):** CEO reviews 5 named Salesforce reports daily (Prospects, Top Prospects, Top Companies, Inactive Case Financing, Inactive Pre-Settlement). These reports exist and are used — the question is whether consultants review them too, or only the CEO. See `SOPs/20260728_Capital-Financing_Daily-Salesforce-Task-Review.md`.
- **Follow-up closure rate definition (partially answered):** CEO's 1-week post-onboarding referral tracking is a de facto definition — firms are asked to send their first referral within 1 week of onboarding, but most take months. This gap is why the task system exists. Whether this 1-week cadence should be enforced on consultants (not just the CEO) is the remaining question.
- Lead quality metrics per source (conferences, internet, referral, outbound email)
- Executive decision points: Victoria performance improvement plan timeline and exit criteria; Brian guardrails escalation path; Audrey side-business boundary enforcement

**SharePoint institutional knowledge rollout (new layer, CEO directive)**
- Training email template and rollout schedule (CEO sending training to all staff; enforcement TBD)
- SharePoint folder structure and governance: where different artifact types live (process docs, SOPs, team notes, client data)
- Accountability mechanism: how CEO will verify team is *using* SharePoint for knowledge capture vs. ad hoc email/chat
- Tools for easy access on mobile/desktop (CEO noted: "I'm not a techie. I'm not really good with cloud services... SharePoint is not very user-friendly")

**Julius — Inactive Account Follow-Up (new process trunk, from Howie dictation 2026-07-28)**
- Julius handles follow-up with all inactive accounts (case financing + pre-settlement) behind the scenes via templated emails and calls.
- **Problem:** He has not had much success with responses and falls **months behind** in his cadence, defeating consistency.
- **CEO judgment:** This should be automated — "if we had it set up from an automation perspective, it probably would be more creative, more effective, and more consistent."
- **Status:** Flagged as ranked want #10 in `xx_howies_wants.md`. High-priority automation candidate. Needs scoping: what time thresholds for active vs. inactive, what the KPI dashboard should look like, whether active/inactive get different automation rules.

---

*End of current-state map. Next artifact: visual linear flow per workflow on the canvas, then the Overall flow joining the five spines. This document will be refreshed post-onboarding as new accountability metrics and SharePoint governance take effect.*
