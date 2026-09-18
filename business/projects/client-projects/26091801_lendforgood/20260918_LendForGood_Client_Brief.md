# LendForGood

Australian crowdfunded small-business lending platform — connects lenders and borrowers, with LendForGood ("LFG") sitting in the middle administering the funding and repayment flow.

**Primary internal contact:** Martina Madrid Sebring — Fractional COO. martina@madridops.com

---

## 1. Client and Organization

- **Legal/trade name:** LendForGood, operating online as lendforgood.io.
- **Headquarters:** Australia *(inferred from "they're Australian based")*.
- **CEO:** Cameron Neil ("Cam"). Previous owner of the Lender Activity Statements process; handover to Martina in progress. Approver of record — sign-off required before any lender-facing send.
- **Co-Founder & CTO:** Renata. Originally scoping a Xero-API-based automation route for lender statements; that effort has since been handed off to Martina (see Section 4), which is why Martina is the one driving this engagement.
- **Fractional COO:** Martina Madrid Sebring (madridops.com). Current process owner for Lender Activity Statements (drafted the SOP, v1.0, 19 August 2026, from Cam's walkthrough) and now owns the Xero automation effort after Renata handed it off.
- A related entity, **"Leaders For Good,"** is referenced as out of scope for this SOP — separate statement format, pending templates and data support from Cam. **Relationship to LendForGood is unconfirmed — do not assume anything here** (could be unrelated, a sister org, a related fund, etc.) until the client clarifies.

> ⚠️ NEEDS INPUT: LFG's registered business name/ABN, HQ address, main phone. *(Client: unknown for now.)*
> ⚠️ NEEDS INPUT: How "Leaders For Good" relates to LendForGood. *(Client: unknown — explicitly do not assume a relationship.)*

---

## 2. Business Profile

LendForGood runs a crowdfunded lending marketplace: borrowers apply for loans, and a pool of many individual lenders each commit ("subscribe") an amount to fund a given loan. Once a subscription campaign is fully committed, LFG collects the pooled funds from lenders, disburses the loan to the borrower, then collects repayments from the borrower on the loan's terms (bullet repayment at term end, e.g. 9 months, or periodic repayment, e.g. quarterly over 12 months) and passes each lender's share of repayment back to them. The borrower side is few; the lender side is many (tens to fifty-plus per report cycle).

Xero is used as the system of record for this loan activity — there is no dedicated loan-servicing module, so invoices and bills are used as internal tracking devices for money owed in each direction *(inferred, detailed in Section 6)*. It is not yet confirmed whether LFG's own operating business accounting (payroll, expenses) lives in the same Xero org as the lender/borrower fund-administration ledger, or is properly separated *(status: TBD, per client)*.

The engagement entered through an existing relationship — JC was walking the client through automation options for an existing manual reporting process. Current phase: discovery/scoping, pre-contract for the larger build (MSA being sent to formalize access to review financial exports). Notably, the Xero automation effort originally sat with the Co-Founder/CTO (Renata) and has since been reassigned to the fractional COO (Martina) — that reassignment is the direct reason this engagement started.

Growth pressure noted: the client is approaching an AU$4 million cumulative-deployed milestone, and reporting overhead is expected to keep scaling as the business grows.

---

## 3. Goals

**Personal Goals**
- Cam wants sign-off/approval load reduced over time — open to full automation of the statement send once accuracy is proven, removing himself as a manual bottleneck.
- Martina wants to stop hand-renaming PDF exports and to have a working system for "getting Xero data out cleanly," now that this has become her responsibility rather than Renata's.

**Business Goals**
- Automate the lender activity statement process end-to-end: pull loan activity per lender from Xero, generate a per-lender PDF, and email it — without manual eyeballing of the contact list or manual file renaming.
- Keep raw financial data out of AI systems entirely; any automation touching lender/borrower money must be a deterministic, rules-based script, not an AI process.
- Resolve reporting-policy ambiguity (cash vs. accrual, exact period end) so the process being automated is actually settled.

---

## 4. Key People — Internal
*(LendForGood's own team)*

**Cameron Neil — CEO**
- Working Style: delegates presentation/format details ("I don't care what the document looks like") but retains sign-off authority on anything lender-facing; built and owns the saved Xero custom report used for statements.
- Relevance: approver/gatekeeper for any lender-facing send; primary decision-maker on the two open policy questions (cash vs. accrual, period end date).
- Watch-point: process handover to Martina is "in progress," not complete — may still be the practical decision-maker during transition.

**Renata — Co-Founder & CTO**
- Working Style: technical owner who was independently scoping a Xero-API automation route (~USD 50/month, still evaluating cheaper alternatives as of 17 August 2026) before handing the whole effort to Martina.
- Relevance: no longer the day-to-day driver of this project, but as Co-Founder/CTO she's the natural technical sign-off if/when a build touches Xero's API or LFG's broader systems. Worth looping in at the architecture stage even though Martina now owns delivery.
- Watch-point: confirm there's no unfinished piece of her original API approach still in flight that could collide with a new build.

**Martina Madrid Sebring — Fractional COO (madridops.com)**
- Working Style: hands-on with the Xero process herself; documented the current manual SOP; already experimenting with Claude on her own to clarify SOP language, suggesting comfort with AI tools for non-financial tasks.
- Relevance: primary day-to-day contact for this engagement. Now owns the Xero automation effort, handed off from Renata — this handoff is the reason she reached out.
- Watch-point: she's fractional, not full-time on-site — factor her availability/bandwidth into scheduling and don't assume LFG-employee-level access to internal systems by default.
- Contact: martina@madridops.com

---

## 5. Key People — External (Vendors & Partners)

None identified in this material beyond the core software vendor (Xero — covered under Technology Stack, not a services vendor here).

---

## 6. Technology Stack

**Xero** — system of record for all loan activity.
- No native loan-servicing object; loan activity is tracked using invoices and bills as internal placeholders rather than a clean ledger. Working model *(inferred from the call's own Claude-assisted clarification)*:
  - **Funding a loan (money out):** Invoice raised **to each lender** for their subscribed amount (lender owes LFG — receivable); a bill is recorded **for the borrower** representing the draw disbursed to them (LFG owes borrower — payable).
  - **Repayment (money back):** Invoice raised **to the borrower** for their scheduled repayment (borrower owes LFG — receivable); a bill is recorded **to each lender** for their share of that repayment (LFG owes lender — payable).
  - A bill to a lender is only raised once LFG confirms the borrower's repayment money is actually coming in.
- Reporting: a saved custom report, **"loan activity statement by lender,"** already exists in Xero > Reporting > Custom Reports (built by Cam). Date range and reporting-basis defaults persist between uses; the "select all loan agreement lines" filter does **not** persist and must be reapplied every time.
- Bank feeds: described as **four accounts** total. Per the call transcript (confirmed by client as the source — no separate written document exists beyond this), the only detail actually spoken was: the AUD account has a live/automatic bank feed; the USD account and at least one "capital account" require manual export from the bank and manual import into Xero. The remaining account(s) and the full four-account structure were not spelled out in the transcript itself — JC was reading from something on screen during the call and paraphrased it live, so only this partial picture is documented.
- Lender/borrower contacts live in Xero's Contacts, with lenders in a dedicated "Lender" group — but that group is not currently filterable down to just "lenders needing a statement this cycle"; that judgment is made by eye.

> ⚠️ NEEDS INPUT: The full detail on all four accounts and the bank-feed setup isn't fully captured anywhere reviewed — only a partial, spoken description exists. If a written reference for this exists separately from the transcript, it would help; otherwise this may need to be confirmed live with Martina or Renata.
> ⚠️ NEEDS INPUT: Confirm whether the LFG operating-business Xero data and the fund-administration (lender/borrower) Xero data are in the same org or separate. *(Client: TBD.)*

**hello@lendforgood.io inbox** — holds the email templates used for the lender statement send; also the required send-from address, which is not the default and must be set manually at send time on every batch.

**LFG document folder** — repository of prior lender-activity-statement PDFs, used only as a naming-convention reference when renaming new exports.

**Claude** — client (Martina) has already used Claude independently to help clarify SOP wording. No financial data has been put in front of an AI tool to date, and the client is explicit that this should not change.

**Python (proposed, not yet built)** — the direction floated on the call for the actual automation: a small, deterministic script to aggregate the ledger export per lender and generate PDFs, specifically chosen so financial data never has to pass through an AI system.

---

## 7. Problem Register

### P-001 — Manual, judgment-based lender list and report generation
- **Area:** Processes
- **Problem:** Every cycle, someone works through the Xero "Lender" contact group by eye to figure out who needs a statement, then re-opens the saved report and re-runs it per contact, reapplying a filter that doesn't persist.
- **Current Thinking:** "There's no real system, you just kind of know which ones" need a report.
- **Reframe:** Eligibility for a statement should be a data property (a tag/flag on the contact) rather than a judgment call re-made from memory every cycle.
- **Approach:** Not started. Candidate for the ledger-export automation once the Xero export is reviewed.

### P-002 — Manual filename renaming
- **Area:** Processes / Tools
- **Problem:** Every exported PDF carries the same generic filename. Renaming each one to the period + lender-name convention is entirely manual, is explicitly called out as the largest time cost in the batch, and skipping it makes the whole batch unusable.
- **Current Thinking:** Renaming is just an unavoidable manual chore after export.
- **Reframe:** Renaming is a mechanical, rules-based mapping (account number → filename) that doesn't require exposing statement content to solve.
- **Approach:** In progress — agreed on the call as the smallest tractable first piece, and one the client can likely run themselves day-to-day using Claude, with light JC involvement.

### P-003 — No end-to-end pipeline from ledger to sent statement
- **Area:** Systems
- **Problem:** There is no automated path from "raw Xero ledger" to "generated PDF" to "emailed to the right lender." Every step downstream of the Xero screen is hand-run.
- **Current Thinking:** Full automation has to happen inside Xero itself, which means paying for full API access — this was Renata's original framing before she handed the effort off.
- **Reframe:** A lightweight external script working off a raw ledger/CSV export can achieve the same outcome, at lower cost and without financial data ever reaching an AI system.
- **Approach:** Not started. Scoping is gated on JC reviewing an actual general-ledger export; pricing to follow once complexity is known. Since ownership has moved from CTO to fractional COO, worth a light technical check-in with Renata before finalizing architecture, but she is no longer expected to be running a parallel effort.

### P-004 — Unsettled reporting policy, and a stated-frequency contradiction
- **Area:** Processes / Governance
- **Problem:** Two decisions are open and are explicitly blocking a full batch run: cash vs. accrual reporting basis, and the exact period end date to use. Separately, the written SOP states the cadence is "Quarterly, with catch-up batches," but the call states the confirmed cadence is twice a year (30 June and 31 December).
- **Current Thinking:** The SOP was documented before these decisions were finalized, and the frequency mismatch hasn't been caught yet.
- **Reframe:** These are policy calls for Cam to make, not defaults to automate around — building automation on top of an unsettled process just automates the ambiguity.
- **Approach:** Not started. Needs to go back to Cam/Martina before any technical design is locked in.

### P-005 — Unverified data separation between business and fund-admin ledgers
- **Area:** Systems / Data
- **Problem:** It isn't yet confirmed whether LFG's own operating business accounting and the lender/borrower fund-administration ledger sit in the same Xero org. A "general ledger" export could pull in private business expenses and payroll alongside loan activity.
- **Current Thinking:** Not yet verified either way — status is TBD per client.
- **Reframe:** This needs confirming before any data leaves Xero, both for the client's own data hygiene and to correctly scope what the export tool needs to filter out.
- **Approach:** Not started. Client to confirm and report back.

---

## 8. Action Plan

**Plan Overview:** Five open problems, clustered mainly in Processes and Systems around the absence of a rules-based Xero-to-PDF-to-email pipeline. The client's stated top priority is the smallest tractable win — automated file renaming — but the real constraint on the bigger build is getting a clean, reviewed data export, which is gated by an MSA, by two of Cam's unresolved policy decisions, and by a data-separation check that hasn't happened yet. Sequencing logic: settle governance/data questions and ship the low-risk renaming automation in parallel first, then scope and build the fuller pipeline once a real export is in hand.

### People
**Problems in scope:** P-004, P-005

- **Workstream: Settle open policy and data questions**
  - Approach: Push the unresolved decisions back to Cam and confirm the data-separation question with whoever has visibility, rather than assuming defaults.
  - What it involves: Get Cam's decision on cash vs. accrual and the period end date; confirm with Martina whether the business and fund-admin ledgers are separated in Xero.
  - Key Result: Written answers to both open questions.
  - Timeline: ~1 week, no dependencies — start immediately.

### Processes
**Problems in scope:** P-001, P-002

- **Workstream: Automate PDF renaming**
  - Approach: Smallest-scope win, agreed on the call — solve the single largest manual time cost first, without needing the full ledger export.
  - What it involves: Define the account-number/period naming convention as a rule; apply it to exported PDFs (client can likely run this themselves with light Claude assistance).
  - Key Result: Manual renaming step removed from the SOP; batch turnaround time drops.
  - Timeline: 1–2 weeks, can start now, runs concurrent with the People workstream above.

### Systems
**Problems in scope:** P-003

- **Workstream: MSA + Xero export review**
  - Approach: Formalize access before touching any financial data, then use a real export to scope the real build.
  - What it involves: Client signs MSA; client logs into Xero and exports the last six months of the general ledger; JC reviews it for structure/complexity.
  - Key Result: Signed MSA and a reviewed export in hand, with a delivered scope and price for the fuller build.
  - Timeline: 1–2 weeks, gated on client Xero access and the P-005 data-separation confirmation.

- **Workstream: Ledger aggregation + PDF generation (rules-based, no AI on financial data)**
  - Approach: A small deterministic script, not an AI process, so lender/borrower financial data never passes through a model.
  - What it involves: Parse the ledger export, aggregate a running per-lender in/out tally, generate the per-lender PDF.
  - Key Result: Script output validated against a prior manually-produced statement batch.
  - Timeline: Starts after export review/pricing; several weeks; ideally informed by the cash-vs-accrual decision from the People workstream.

- **Workstream: Automated email delivery**
  - Approach: Match lender to email by account number (not name), so the sender never needs to know who the lender is by name.
  - What it involves: Auto-send the generated PDF with fixed template copy from hello@lendforgood.io; ideally bundled into the same portal-style flow as generation ("drop the file, confirm emails are ready, hit send").
  - Key Result: End-to-end send working without per-contact manual work.
  - Timeline: Starts once the aggregation/PDF workstream is validated; tail-end concurrent with it.

**Recommended Sequence**
1. Settle policy/data questions with Cam and Martina (no dependency — start now).
2. Ship the PDF-renaming automation in parallel (no dependency on #1).
3. Sign MSA and obtain a reviewed Xero export (informed by, but not strictly blocked by, #1).
4. Deliver scope and pricing for the full build, based on the reviewed export (depends on #3).
5. Build ledger aggregation + PDF generation (depends on #4; best informed by the cash/accrual decision from #1).
6. Build automated email delivery (depends on #5; can ship as part of the same release).

---

## 9. Engagement Metrics

Ungraded — baseline. This is the first documented meeting.

- **Comprehension:** Client clearly understands their own manual process (documented it themselves) but is less certain about the underlying Xero invoice/bill logic — JC had to walk through it live on the call.
- **Adherence:** N/A yet — no plan has been handed over.
- **Adoption:** N/A yet.
- **Velocity:** Client is motivated and moving quickly (MSA to be signed immediately post-call) — watch that eagerness doesn't outrun the still-unresolved policy questions (P-004).
- **Volume:** Low so far — one scoped problem area, appropriately small for a first engagement.

---

## 10. Recommended Service Tier

This reads as a single, well-bounded automation project rather than an open-ended AI-roadmap retainer: one clear pain point (manual, security-sensitive reporting), a client that explicitly wants a narrow, rules-based (non-AI) solution, and a small number of concurrent workstreams. Recommend a scoped, fixed-price project engagement — quick win (renaming automation) delivered first, followed by a priced build for the full ledger-to-email pipeline once the Xero export has been reviewed.

> ⚠️ NEEDS INPUT: No dollar figures were discussed on this call for either the quick win or the full build — pricing to be set once the Xero export is reviewed. *(Client: TBD.)*

---

## Open Questions for You

1. LendForGood's registered legal name/ABN, HQ address, and main phone. *(unknown for now)*
2. How does "Leaders For Good" relate to LendForGood? *(unknown — assume nothing)*
3. Whether a written document exists (separate from the call transcript) with the full four-accounts/bank-feed detail — the transcript only captures a partial, spoken version of it.
4. Is LFG's operating business accounting separated from the fund-administration (lender/borrower) ledger in Xero, or in the same org? *(TBD)*
5. Pricing — none discussed yet; flag once you've reviewed the export and have a number in mind. *(TBD)*
