---
title: "Capital Financing — Contracting, Funding & Accounts Receivable (SOP)"
date: 2026-08-07
tags: [client, project, sop]
ai: claude
status: needs-attention
source: Live screen-share walkthrough with Yasmine Swain, Director of Contracting and Servicing
---

# Capital Financing — Contracting, Funding & Accounts Receivable Process

**Standard Operating Procedure**
Operations — Post-Underwriting Case Flow

| Field | Value |
| --- | --- |
| Document Owner | Yasmine Swain (Director of Contracting and Servicing) |
| Department | Contracting / Funding / Accounts Receivable / Payoffs |
| Reviewed By | — (not yet reviewed by Yasmine) |
| Frequency | Event-driven (per case) — AR follow-up sub-process runs on a recurring cadence, see Section 5 |
| Last Updated | August 7, 2026 |

## 1. Purpose

This SOP documents everything that happens to a Capital Financing case from the moment underwriting approves it through final repayment and file close-out. It covers Contracting (agreement issuance and execution), Funding (disbursement), Accounts Receivable (tracking to settlement), and Payoffs — the four functions Yasmine owns or oversees. The goal is a process detailed enough that someone could step into this role and run it end-to-end, and clear enough to show where automation could remove manual, unreminded work.

This document is written for someone stepping into the Contracting/Funding/AR role with a general understanding of case-financing operations, but no prior knowledge of Capital Financing's specific systems or conventions.

## 2. Background & Key Concepts

**What is JB?**
JB — also called Mighty, also called Justice Bolt — is one platform referred to interchangeably by staff under all three names. It is the core loan-servicing system where applications, underwriting status, contracting, disbursement, and lien/AR tracking all live.

**How is case-expense funding distinguished from pre-settlement funding in JB?**
There is no dedicated field for this. Case-expense files are manually tagged **"LIT"** after the client's name, and the same LIT tag is duplicated into the "Capital Providers" field at 100% specifically so a report can later isolate case-expense volume — there is no other way to filter for it in the current system.

**What is FormStack, and how is it accessed?**
FormStack by Intelistack is the e-signature platform used to send funding agreements for signature. It is accessed through a **single shared login for the whole Contracting group email**, not individual per-user accounts. This was a direct point of comparison against Segue, who proposed offering individual logins but could not actually demonstrate that feature working during their own demo.

**What are the contract types?**
The contract type is decided during underwriting, before a file reaches Contracting.

| Model | Product | Fee | Term |
| --- | --- | --- | --- |
| 25% model (most-used, "advertised") | Pre-settlement | 25% of principal, accruing quarterly (every 90 days) | 12 months, all fees terminate after |
| 5% Simple Agreement | Pre-settlement | 5% | Capped at 48 months (recently changed from open-ended, driven by varying state caps on contract terms) |
| Case-expense (current model) | Case-expense | 15% | First three months charged upfront/automatically at funding; mechanics past month three `[TO CONFIRM]` |
| Case-expense (old model) | Case-expense | Monthly, from funding date | Discontinued — do not use |

**What are the disbursement methods, and what are the thresholds?**
Three payment rails exist, each with its own cap and authorization limits.

| Method | System | Cap | Used for | Authorization |
| --- | --- | --- | --- | --- |
| Push-to-Debit | AppPay | $2,500 (under review to raise) | Plaintiffs only — never law firms | No individual threshold; requires debit-card photo verification |
| Direct Deposit | Bank/treasury | None | Plaintiffs and law firms | Audra: $25K · Chanel: $10K · Yasmine: unlimited |
| Wire | Bank/treasury | None | Larger or complex payments | Yasmine and Danielle only |

If a push-to-debit amount exceeds $2,500, it is split across multiple transactions on different dates rather than switched to another method. Law-firm reimbursements always go by direct deposit or check into the firm's operating account, never push-to-debit.

**What is Funding Exchange?**
Funding Exchange is an external, cross-funding-company platform used to check whether a client already has funding or liens with another company before advancing money, and to log new liens once funded so other funding companies can see them. This prevents "stacking" — a real problem at settlement, since whichever funder advanced first gets repaid first if settlement proceeds run short. Intake runs the pre-underwriting check (client name, DOB, last-4 SSN); Contracting logs the lien after funding.

**What is the Payoff process?**
A dedicated shared inbox receives two types of requests: standard payoff/balance requests, and reduction requests (a firm asking to settle for less than the full balance). Reduction requests always route to Howie for approval or denial before any reduced-payoff letter is generated.

## 3. Roles & Responsibilities

| Role / Person | Responsibility in This Process |
| --- | --- |
| Yasmine Swain | Owns Contracting, Funding (jointly with Danielle), and AR oversight. Personally carries 261 AR files. Unlimited direct-deposit authorization; one of two people authorized to send a wire. Handles payoff requests and Funding Exchange logging. |
| Audra | Contracting and Funding for law firms M–Z (by firm name). Direct-deposit authorization up to $25,000. |
| Chanel | Contracting and AR for law firms A–L (by firm name). Direct-deposit authorization up to $10,000. Carries 187 AR files. |
| Diana | Accounts Receivable (VA). Carries 313 AR files. |
| Jalicia | Accounts Receivable (VA, part-time). Carries 323 AR files; also runs client-requested quarterly/monthly reports. |
| Danielle | Funding; final close-out authority in QuickBooks. One of two people authorized to send a wire. |
| Christy (or Howie, when covering) | Underwriting — approves the case and selects the contract type before it reaches this process. Owns the decision, not the execution documented here. |
| Howie | Approves or denies all payoff reduction requests. |

## 4. Systems & Tools Used

| Tool | Purpose |
| --- | --- |
| JB (Mighty / Justice Bolt) | Core loan-servicing system — applications, contracting, disbursement, lien and AR tracking. |
| FormStack by Intelistack | E-signature platform for funding agreements, accessed via a shared Contracting group login. |
| AppPay | Push-to-debit disbursements only. |
| Bank / treasury system | Direct deposit and wire disbursements. |
| Funding Exchange | Cross-funding-company lien check and logging, to prevent stacked funding. |
| QuickBooks | Final financial reconciliation and close-out. |
| Salesforce | One confirmed touchpoint: flipping a record to "Approved" status, and adding newly-discovered attorney contacts to a firm's record. |
| Outlook | Templated client and law-firm confirmation emails. |
| Group email inboxes | `intake@injuryfinancing.com`, a Contracting group inbox, and a separate Payoff group inbox `[TO CONFIRM: exact Contracting and Payoff inbox addresses]`. |

## 5. Schedule

This process is **event-driven** — it starts whenever underwriting approves a case, not on a calendar cadence. One sub-process runs on a recurring basis:

- **Per case (as triggered):** Steps 1–14 below, from receiving an approved case through disbursement and confirmation.
- **Ongoing, per active file:** AR follow-up (Step 15) — default cadence 90 days once a case is in litigation, adjusted at Yasmine's discretion for firms with an established relationship (e.g., 120 days for high-volume, low-risk firms). No automated reminders exist for this today.
- **As requests arrive:** Payoff and reduction handling (Step 16), deposit processing and close-out (Steps 17–19).

## 6. Step-by-Step Process

### Step 1: Receive the Approved Case from Underwriting
| Field | Detail |
| --- | --- |
| **Inputs** | A case underwriting has approved. |
| **Where inputs come from** | Underwriting (Christy, or Howie while she's out) approves the case in JB and notifies Contracting, typically by tagging the assigned person directly on the file. |
| **Software & tools** | JB |
| **Who is responsible** | Whoever is assigned by the A–L/M–Z law-firm split (Chanel or Audra), or whoever is tagged directly on a non-standard file. |
| **Outputs** | A case ready for Contracting to begin agreement issuance. |
| **Where outputs go** | Feeds Step 2 (case-expense only) or Step 3. |
| **Notes** | If this is case-expense funding, confirm the file is tagged "LIT" after the client's name in JB, and that the tag is duplicated into the "Capital Providers" field at 100%. |

### Step 2: Collect the Acknowledgement Letter (Case-Expense Only)
| Field | Detail |
| --- | --- |
| **Inputs** | Underwriting approval on a case-expense file. |
| **Where inputs come from** | Step 1. |
| **Software & tools** | JB; Email |
| **Who is responsible** | Assigned Contracting staff (Chanel or Audra) |
| **Outputs** | A signed acknowledgement letter from the plaintiff, confirming the law firm is taking out funding against their case. |
| **Where outputs go** | Uploaded/logged in JB; unblocks Step 3. |
| **Notes** | Reach out to the attorney or firm contact directly to request it. Log a note in JB and follow up roughly every couple of days — there is no automated reminder for this step. If the firm goes unresponsive after several follow-ups, close the application in JB; it can be reopened easily if the firm re-engages later. Skip this step entirely for pre-settlement files. |

### Step 3: Generate the Funding Agreement
| Field | Detail |
| --- | --- |
| **Inputs** | Approved case; contract type selected during underwriting (see Section 2 table); signed acknowledgement letter (case-expense only). |
| **Where inputs come from** | JB |
| **Software & tools** | JB |
| **Who is responsible** | Assigned Contracting staff |
| **Outputs** | A generated funding agreement, as a Word document. |
| **Where outputs go** | Uploaded into FormStack (Step 4). |
| **Notes** | Confirm which contract model applies before generating — see the contract-type table in Section 2. |

### Step 4: Set Up the FormStack Signature Template
| Field | Detail |
| --- | --- |
| **Inputs** | Generated agreement document. |
| **Where inputs come from** | Step 3. |
| **Software & tools** | FormStack by Intelistack |
| **Who is responsible** | Assigned Contracting staff |
| **Outputs** | Document uploaded with a pre-built signature-field template applied, matching the contract-type and funding-method combination (e.g., "25% + ACH direct deposit"). |
| **Where outputs go** | Feeds Step 5. |
| **Notes** | Signature fields are pre-mapped by template — check placement rather than mapping from scratch, and drag fields into position if anything landed incorrectly. |

### Step 5: Add Signers and Send
| Field | Detail |
| --- | --- |
| **Inputs** | Document with signature template applied. |
| **Where inputs come from** | Step 4. |
| **Software & tools** | FormStack |
| **Who is responsible** | Assigned Contracting staff |
| **Outputs** | Agreement sent for signature, named using the convention: client's last name, attorney's last name, advance number (e.g., "Smith Johnson ADV1"). |
| **Where outputs go** | FormStack tracking (Step 6). |
| **Notes** | Only an attorney may sign a case-expense contract, unless the firm has given written permission for a paralegal to sign on their behalf — confirm that permission exists in writing before accepting a non-attorney signature. For pre-settlement agreements, the plaintiff signs. |

### Step 6: Track Signature Status
| Field | Detail |
| --- | --- |
| **Inputs** | Sent agreement. |
| **Where inputs come from** | FormStack dashboard — "Out for Signature" and "Signed" views. |
| **Software & tools** | FormStack; Email |
| **Who is responsible** | Assigned Contracting staff |
| **Outputs** | Confirmed signature status; reminders sent if overdue. |
| **Where outputs go** | Feeds Step 7 once signed. |
| **Notes** | Check FormStack daily. Cross-check the shared email inbox each morning as a second check against JB. FormStack sends automatic reminders, but manual reminders are also standard practice — roughly every couple of days if overdue, with no fixed SLA currently documented. |

### Step 7: Process the Signed Contract
| Field | Detail |
| --- | --- |
| **Inputs** | Fully signed agreement. |
| **Where inputs come from** | FormStack. |
| **Software & tools** | FormStack; JB |
| **Who is responsible** | Assigned Contracting staff |
| **Outputs** | Signed document uploaded into JB, tagged "signed contract." |
| **Where outputs go** | Marks the file executed; feeds Step 8. |
| **Notes** | None. |

### Step 8: Confirm Terms with the Client by Phone
| Field | Detail |
| --- | --- |
| **Inputs** | Executed agreement. |
| **Where inputs come from** | Step 7. |
| **Software & tools** | Phone |
| **Who is responsible** | Assigned Contracting staff |
| **Outputs** | Client understands and confirms the terms of the contract. |
| **Where outputs go** | Unblocks disbursement (Steps 9–10). |
| **Notes** | This call happens before releasing any funds, regardless of which disbursement method will be used. |

### Step 9: Collect Disbursement Verification
| Field | Detail |
| --- | --- |
| **Inputs** | Confirmed disbursement method. |
| **Where inputs come from** | Client, following the Step 8 call. |
| **Software & tools** | Email; JB (for storage) |
| **Who is responsible** | Assigned Contracting staff |
| **Outputs** | A photo of the debit card (push-to-debit) or a voided check / bank letter with name, account number, and routing number (direct deposit). |
| **Where outputs go** | Used to execute Step 10. |
| **Notes** | None. |

### Step 10: Disburse Funds
| Field | Detail |
| --- | --- |
| **Inputs** | Verification from Step 9; disbursement amount and method. |
| **Where inputs come from** | Steps 8–9. |
| **Software & tools** | AppPay (push-to-debit); Bank/treasury system (direct deposit, wire) |
| **Who is responsible** | Funding trunk — Danielle, Audra, or Yasmine, per the authorization table in Section 2. |
| **Outputs** | Funds disbursed. |
| **Where outputs go** | Feeds Step 11. |
| **Notes** | See the disbursement-method table in Section 2 for caps and authorization limits. If a push-to-debit amount exceeds $2,500, split it across multiple transactions on different dates. |

### Step 11: Move the File to Funded and Adjust Dates
| Field | Detail |
| --- | --- |
| **Inputs** | Confirmed disbursement. |
| **Where inputs come from** | Step 10. |
| **Software & tools** | JB |
| **Who is responsible** | Assigned Contracting/Funding staff |
| **Outputs** | File status moved from Approved to Funded, then to Lien. Agreement-signed date and funded date adjusted if they differ from system defaults. |
| **Where outputs go** | Feeds Step 12. |
| **Notes** | Fee accrual starts on the day funds are actually released, not the day the contract was signed — these two dates are tracked separately. If this is a repeat advance on an existing case, it keeps the same client/case ID and receives the next sequential advance number. |

### Step 12: Log the Lien in Funding Exchange
| Field | Detail |
| --- | --- |
| **Inputs** | Newly funded lien. |
| **Where inputs come from** | Step 11. |
| **Software & tools** | Funding Exchange |
| **Who is responsible** | Assigned Contracting staff |
| **Outputs** | New lien visible to other funding companies. |
| **Where outputs go** | Funding Exchange platform (external). |
| **Notes** | Confirm intake already ran the pre-underwriting check (client name, DOB, last-4 SSN) before this case was approved — this step is the corresponding post-funding log entry, not the check itself. |

### Step 13: Send Confirmation to Client and Law Firm
| Field | Detail |
| --- | --- |
| **Inputs** | Funded case. |
| **Where inputs come from** | Step 11. |
| **Software & tools** | Outlook; JB (for the generated confirmation letter) |
| **Who is responsible** | Assigned Contracting staff |
| **Outputs** | Confirmation email sent to the client and everyone on the file at the law firm (attorney and any paralegal contacts), with the signed agreement attached. |
| **Where outputs go** | Client and firm inboxes; Contracting is CC'd. |
| **Notes** | Built from an Outlook template (swap in client name and funded date) plus the JB-generated payoff/funding confirmation letter. |

### Step 14: Update Salesforce
| Field | Detail |
| --- | --- |
| **Inputs** | Funded, confirmed case. |
| **Where inputs come from** | Step 13. |
| **Software & tools** | Salesforce |
| **Who is responsible** | Assigned Contracting staff |
| **Outputs** | Record status flipped to "Approved" — the only Salesforce touchpoint in this entire process for a standard file. |
| **Where outputs go** | Salesforce. |
| **Notes** | If a new attorney is discovered at an existing firm client, add them as a contact under that firm's Salesforce record so consultants know who's there. This status flip used to trigger marketing drip emails; those are currently paused, reason `[TO CONFIRM]`. |

### Step 15: Track the Case in Accounts Receivable
| Field | Detail |
| --- | --- |
| **Inputs** | Funded lien, active until settlement. |
| **Where inputs come from** | JB. |
| **Software & tools** | JB; Email; Phone |
| **Who is responsible** | Jalicia, Diana, Yasmine, or Chanel, per assigned file. |
| **Outputs** | Periodic firm check-ins confirming case status. |
| **Where outputs go** | Logged as notes in JB. |
| **Notes** | Follow-up cadence is status-based (e.g., 90 days once in litigation) and adjusted at your discretion for the relationship — an established, high-volume firm might get 120 days instead. No automated reminders exist for this step; it is fully manual. |

### Step 16: Handle a Payoff or Reduction Request
| Field | Detail |
| --- | --- |
| **Inputs** | Inbound request to the Payoff group inbox. |
| **Where inputs come from** | Law firm. |
| **Software & tools** | Payoff group inbox; JB |
| **Who is responsible** | Yasmine (standard requests); Howie (reduction approval) |
| **Outputs** | For a standard request: a payoff confirmation letter sent with the signed agreement. For a reduction request: an approval or denial from Howie, then a reduced-payoff letter if approved. |
| **Where outputs go** | Sent to the firm, CC'ing Contracting and the client. |
| **Notes** | Pull the current balance and lien detail from JB for standard requests. Route reduction requests to Howie before generating or sending anything. |

### Step 17: Process a Settlement Deposit
| Field | Detail |
| --- | --- |
| **Inputs** | Settlement check received. |
| **Where inputs come from** | Mail/deposit process, handled by the VA who manages deposits. |
| **Software & tools** | JB |
| **Who is responsible** | Deposit VA logs it; assigns to Yasmine. |
| **Outputs** | Deposit logged, tagged to Howie and Danielle, with check number(s) and deposit date noted. |
| **Where outputs go** | Assigned to Yasmine, awaiting bank clearing. |
| **Notes** | No follow-up date is needed at this point — it's awaiting clearing, not a chase. |

### Step 18: Reconcile Against QuickBooks
| Field | Detail |
| --- | --- |
| **Inputs** | Cleared deposit. |
| **Where inputs come from** | Bank, the next business day after Step 17. |
| **Software & tools** | JB; QuickBooks |
| **Who is responsible** | Yasmine |
| **Outputs** | Confirmed match between JB record and QuickBooks. |
| **Where outputs go** | File assigned to Danielle for final close-out. |
| **Notes** | None. |

### Step 19: Close the File
| Field | Detail |
| --- | --- |
| **Inputs** | Reconciled deposit. |
| **Where inputs come from** | Step 18. |
| **Software & tools** | JB; QuickBooks |
| **Who is responsible** | Danielle |
| **Outputs** | File marked closed in JB, with how it closed recorded (attorney paid it, client paid it directly, or another funding company bought out the lien — with that company's name logged); file closed out in QuickBooks. |
| **Where outputs go** | Case fully closed. |
| **Notes** | Client-direct payoff does happen occasionally and should be recorded as such rather than assumed to always be the attorney. |

## 7. Exception Handling

**Non-Standard File Assignment**
Files don't always follow the standard A–L/M–Z split — a file approved directly by Howie (e.g., while Christy is out) may get tagged to whoever's available rather than the "correct" owner by the letter split. `[TO CONFIRM: is there a rule for reassigning these afterward, or is it purely ad hoc?]`

**Non-Attorney Signers**
Only an attorney can sign a case-expense contract unless the firm has given written permission for a paralegal to sign on their behalf. Get that permission in writing before accepting the signature — do not proceed on a verbal assurance alone.

**Unresponsive Firm — Acknowledgement Letter or Signature**
If a firm goes unresponsive after several follow-ups on an acknowledgement letter or a signature request, close the application in JB. It can be reopened easily if the firm re-engages later — do not leave it open indefinitely.

**Reduction Requests**
Never generate or send a reduced-payoff letter without Howie's explicit approval first. This is the one decision in this entire process that isn't Contracting's or Yasmine's to make alone.

**Repeat Advances on the Same Case**
A single case/client can have many advances over time — one case on record had 24 separate advances. All stay under the same client/case ID in JB, incrementing the advance number each time; do not create a new case record for a repeat advance.

**Case-Expense Fee Mechanics Past Month Three**
The current case-expense model charges the first three months' fees upfront at funding. What happens after month three is `[TO CONFIRM]` — do not assume it mirrors the pre-settlement quarterly-accrual model without checking.

*Capital Financing — Confidential & Internal Use Only*
