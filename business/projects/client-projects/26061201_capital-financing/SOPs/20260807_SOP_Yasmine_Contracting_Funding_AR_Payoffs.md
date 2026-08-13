---
title: "SOP — Contracting, Funding & Accounts Receivable (Yasmine's Role)"
date: 2026-08-XX
tags: [client, project, task]
ai: claude
status: needs-attention
---

# SOP — Contracting, Funding & Accounts Receivable

## Summary

Standard operating procedure for the Director of Contracting and Servicing role at Capital Financing: everything that happens to a case from the moment underwriting approves it through to final repayment and file close-out. Covers Contracting, Funding, Accounts Receivable, and Payoffs — the four functions Yasmine owns or oversees. Detailed enough that someone could step into the role and run it end-to-end. Source: live screen-share walkthrough with Yasmine in JB (Mighty/Justice Bolt), 2026-08-XX — see [[../xx_Project_Learnings]] for call context and [[../20260616-Workflow-Map-Capital-Financing-merged]] Workflow 1 Steps 5–8, Workflow 2 Steps 1–7, and Workflow 6 for how this fits the company-wide flow.

## Context

This is the back-of-house half of every funded case — underwriting decides *whether* to fund; this SOP covers everything that happens *after* that decision to actually get money out the door and, eventually, back in. `status: needs-attention` because several fields marked `[TO CONFIRM]` below still need direct confirmation with Yasmine, and this is the first full write-up of the role — it hasn't yet been reviewed by her for accuracy.

## Content

### Systems used

- **JB (also called Mighty, also called Justice Bolt — same platform, staff use all three names interchangeably)** — the core loan-servicing system. Applications, underwriting status, contracting, disbursement, AR, and lien tracking all live here.
- **FormStack by Intelistack** — e-signature platform for funding agreements. Accessed via a **single shared login for the whole Contracting group email**, not individual accounts.
- **AppPay** — separate app used only for push-to-debit disbursements.
- **Company bank/treasury system** — direct deposit and wire disbursements.
- **Funding Exchange** — external cross-funding-company platform to check for and log liens, preventing "stacked" funding across companies.
- **QuickBooks** — final reconciliation and close-out.
- **Salesforce** — one touchpoint only: flipping a record to "Approved" status, and adding newly-discovered attorney contacts to a firm's record.
- **Outlook** — templated client/firm confirmation emails.
- **Group email inboxes** — `intake@injuryfinancing.com`, a Contracting group inbox, and a separate Payoff group inbox. `[TO CONFIRM: exact addresses for the Contracting and Payoff inboxes.]`

### Team & ownership

- **Yasmine** — owns Contracting, Funding (jointly with Danielle), and AR oversight; personally carries 261 AR files; unlimited direct-deposit authorization; one of two people (with Danielle) authorized to send a wire.
- **Audra** — Contracting + Funding + Payoffs; law firms **M–Z** by firm name; direct-deposit authorization up to $25,000.
- **Chanel** — Contracting + AR; law firms **A–L** by firm name; direct-deposit authorization up to $10,000; 187 AR files.
- **Diana** — Accounts Receivable (VA); 313 files.
- **Jalicia** — Accounts Receivable (VA, part-time); 323 files; also runs client-requested quarterly/monthly reports.
- **Danielle** — Funding + final close-out authority in QuickBooks; one of two people authorized to send a wire.
- Law-firm assignment is by **law firm name** (not attorney name) — Chanel A–L, Audra M–Z.

### Step-by-step procedure

**1. Case arrives approved from underwriting**
Underwriting (Christy, or whoever is covering) approves a case in JB and notifies Contracting — typically by tagging the assigned person directly on the file if it's not following the standard A–L/M–Z split (e.g., a file Howie approved personally may get tagged to whoever's available). Case-expense files are tagged **"LIT"** after the client's name in JB, since there is no dedicated field distinguishing case-expense from pre-settlement funding — this is a manual workaround, and it's also duplicated into the "Capital Providers" field (at 100%) purely so a report can isolate case-expense volume later.

**2. Case-expense only — collect the Acknowledgement Letter**
Before a case-expense funding agreement can be sent, the law firm must get its own client (the plaintiff) to sign an acknowledgement letter confirming the firm is taking out funding against their case. Reach out to the attorney/firm to request it, log a note in JB, and follow up roughly every couple of days until it's returned. There is no automated reminder for this step — it's a manual chase. If a firm goes unresponsive after several follow-ups, close the application in JB (it can be reopened easily later if the firm re-engages).

**3. Generate and send the funding agreement**
In JB, generate the contract as a Word document. The contract type was already decided during underwriting — see the **Contract Type Reference** table below. Upload the generated document into FormStack. Select the pre-built signature template matching the specific contract-type + funding-method combination (e.g., "25% + ACH direct deposit") — this template has signature fields pre-mapped to the document, so double-check placement rather than mapping from scratch. Add signers: the plaintiff and/or the attorney, depending on agreement type (only an attorney can sign a case-expense contract, unless they've given written permission for a paralegal to sign on their behalf — confirm this in writing before accepting a non-attorney signature). Name the file using the convention: **client's last name + attorney's last name + advance number** (e.g., "Smith Johnson ADV1"; case-expense agreements use the same convention). Send.

**4. Track signature status**
Check FormStack daily: "Out for Signature" for anything still pending, "Signed" for anything complete. FormStack sends its own automatic reminders, but also manually cross-check the shared email inbox each morning as a double-check — JB will show when something's been signed, but the email inbox check catches anything the system might have missed. Send a manual reminder if a signature is overdue; there's no fixed SLA for this today, roughly every couple of days is standard practice.

**5. Process the signed contract**
Once signed, download the completed document from FormStack and upload it into JB, tagged "signed contract." This effectively marks the file as executed.

**6. Confirm disbursement details with the client**
Before releasing any funds, always call the plaintiff client directly to review the terms of the contract/loan with them — this happens regardless of which disbursement method will be used. If disbursing by push-to-debit or direct deposit, get the required verification: a photo of the debit card (push-to-debit) or a voided check / bank letter with name, account number, and routing number (direct deposit).

**7. Disburse funds — pick the right rail**
See the **Disbursement Method Reference** table below for thresholds and authorization limits. Law-firm-side payments (case-expense reimbursements) are always direct deposit or check into the firm's operating account — never push-to-debit.

**8. Move the file to Funded**
In JB, move the file from Approved to Funded. Adjust the **agreement-signed date** and the **funded date** if they differ from the system defaults — these are tracked separately, since interest/fee accrual starts on the day funds are actually released, not the day the contract was signed. Once funded, the file becomes a **lien** in JB. If this is a repeat advance on an existing case, it keeps the same client/case ID and gets the next sequential advance number.

**9. Log the lien in Funding Exchange**
Confirm the case was already checked in Funding Exchange before underwriting (intake's responsibility, using client name, DOB, last-4 SSN, to rule out existing liens with other funding companies). Once this case is funded, log the new lien into Funding Exchange so other funding companies can see it and avoid stacking.

**10. Send confirmation**
Send a confirmation email/letter to the client and everyone on the file at the law firm (attorney and any paralegal contacts) — built from an Outlook template (swap client name and funded date) plus a JB-generated payoff/funding confirmation letter, with the signed agreement attached. CC Contracting on all outbound law-firm communications for this file.

**11. Update Salesforce (single touchpoint)**
Flip the Salesforce record's status to "Approved." This is the only time Contracting touches Salesforce for a standard file. If a new attorney is discovered at an existing firm client, add them as a contact under that firm's Salesforce record so consultants know who's there.

**12. AR tracking until settlement**
Follow up with the firm periodically to check case status — status-based default cadence (e.g., 90 days once in litigation), adjusted at your discretion for the relationship (an established, high-volume firm might get 120 days instead). No automated reminders exist for this — it's tracked manually per file.

**13. Handle a payoff or reduction request**
Requests come into the dedicated Payoff group inbox.
- **Standard payoff request:** pull the current balance/lien detail from JB, generate the payoff confirmation letter (JB template), and send it with the signed agreement — CC Contracting and the client.
- **Reduction request** (firm asking to settle for less than the full balance): route to **Howie** for approval or denial before generating or sending anything.

**14. Process a settlement deposit**
When a check arrives, the VA who handles deposits logs it, tags Howie and Danielle, and assigns the file to you — noting check number(s) and deposit date. No follow-up date is needed yet; it's awaiting bank clearing.

**15. Reconcile**
The next business day (once the deposit clears), match the JB record against QuickBooks. Once confirmed, assign the file to Danielle for final close-out.

**16. Close the file**
Danielle marks the file closed in JB, recording how it closed — attorney paid it, client paid it directly (does happen occasionally), or another funding company bought out the lien (log that company's name) — and closes it out in QuickBooks.

### Contract Type Reference

| Model | Product | Fee | Term |
| --- | --- | --- | --- |
| 25% model (most-used, "advertised") | Pre-settlement | 25% of principal, accruing quarterly (every 90 days) | 12 months, all fees terminate after |
| 5% Simple Agreement | Pre-settlement | 5% | Capped at 48 months (changed from open-ended; driven by varying state caps on contract terms) |
| Case-expense (current model) | Case-expense | 15% | First three months charged upfront/automatically at funding; mechanics past month three `[TO CONFIRM]` |
| Case-expense (old model, discontinued) | Case-expense | Monthly, from funding date | Discontinued — no longer used |

Contract type/model is decided during **underwriting**, not by Contracting — by the time a file reaches this SOP, the model is already chosen.

### Disbursement Method Reference

| Method | System | Cap | Used For | Authorization |
| --- | --- | --- | --- | --- |
| Push-to-Debit | AppPay | $2,500 (under review to raise) | Plaintiffs only — never law firms | No individual threshold; requires debit-card photo verification |
| Direct Deposit | Bank/treasury | None | Plaintiffs and law firms | Audra: $25K · Chanel: $10K · Yasmine: unlimited |
| Wire | Bank/treasury | None | Larger/complex payments | Yasmine and Danielle only |

If a push-to-debit amount exceeds the $2,500 cap, split it across multiple transactions on different dates rather than switching methods.

### Special cases

- **Non-standard file assignment.** Files don't always follow the standard A–L/M–Z split — a file approved directly by Howie (e.g., while Christy is out) may get tagged to whoever's available rather than the "correct" owner by the letter split. Reassign to the correct owner once things settle, or leave as-is if already in motion — `[TO CONFIRM: is there a rule for this, or is it purely ad hoc?]`.
- **Non-attorney signers.** Only an attorney can sign a case-expense contract unless the firm has given **written permission** for a paralegal to sign on their behalf. Get that permission in writing before accepting the signature.
- **Repeat advances.** A single case/client can have many advances over time (one example on record: 24 separate advances against one client's case) — all under the same client/case ID in JB, incrementing the advance number each time.

### Related SOPs to create (flagged during this walkthrough)

- Underwriting decision process (Christy's side) — referenced constantly here but owned elsewhere; see [[../20260616-Workflow-Map-Capital-Financing-merged]] Shared Sub-Layer Sub-Step B.
- Funding Exchange cross-check procedure (currently intake's responsibility pre-underwriting) — not yet its own SOP.
- Salesforce marketing-drip sequence that used to trigger off the "Approved" status flip — currently paused; worth documenting once/if it's decided whether to resume it.

## Next steps

- Review this SOP with Yasmine directly for accuracy before it's considered final — flip `status` to `ok` once confirmed.
- Resolve the `[TO CONFIRM]` items above (Contracting/Payoff inbox addresses, case-expense fee mechanics past month three, non-standard assignment rule).
- Cross-reference this SOP against want #15 in [[../xx_howies_wants]] (referral-gap detection + automated follow-up) — the manual AR tracking cadence in Step 12 is the exact process that automation is meant to replace.
- Once Kaz's conversation is logged, check whether any of the "no automation exists" points here (AR reminders, Salesforce drip status) get resolved or corrected.
