---
title: "Lender Activity Statements SOP"
date: 2026-08-19
tags: [client, project]
ai: human
status: needs-attention
---

## Summary
LendForGood's SOP for generating and sending lender activity statements from Xero — a per-lender statement of loan payment history, sent to the lender with a short accompanying email.

## Context
Drafted by Martina Madrid Sebring (COO) from Cam Neil's (CEO) 21 July 2026 walkthrough, during the process handover from Cam to Martina. v1.0, drafted 19 August 2026.

## Content

| Field | Detail |
|---|---|
| Process owner | Martina Madrid Sebring, COO |
| Previous owner | Cameron Neil, CEO. Handover in progress. |
| Approver | Cameron Neil. Sign off required before any lender send. |
| Frequency | Quarterly, with catch up batches to clear overdue periods *(note: the 2026-09-18 discovery call confirmed actual cadence is twice a year — 30 June and 31 December — see brief P-004)* |
| Systems used | Xero, hello@lendforgood.io inbox, LFG document folder |
| Version | 1.0, drafted 19 August 2026 |
| Source | Cam walkthrough, LFG Quarterly Operations and Funding Strategy Meeting, 21 July 2026 |

### 1. Purpose
Produce a per-lender activity statement from Xero showing each lender's loan payment history, and send it to the lender with a short accompanying email. This is a lender-facing communication — not a company financial statement, not board reporting.

### 2. Scope
Applies to all contacts assigned to the Lender group in Xero who have had loan activity in the reporting period.
**Out of scope:** Leaders For Good lender activity statements — separate format, pending templates and data support from Cam.

### 3. Before you start — two open decisions, confirm with Cam first
1. Reporting basis: cash or accrual (see trade-off table below).
2. Period end date: Cam's demo used 30 June 2026 (FY end) — confirm whether this batch runs to FY end or a more current date.

Do not run the full batch until both are settled. Also confirm with Renata whether the Xero API automation is close enough to landing to change the approach — as of 17 August she was still looking for a route that avoids the cost of full Xero API access.

### 4. Access required
- Xero, with reporting and contacts access
- hello@lendforgood.io inbox and its email templates
- The LFG folder holding prior lender activity statement PDFs, for the naming convention

### 5. Procedure

**1. Build the lender list** — Xero > Contacts > Lender group. Keep open on a second screen; work through it. Every contact in this group has had an invoice or bill raised against them. The group list may not be exportable or printable — work from screen.

**2. Open the saved custom report** — Xero > Reporting > Custom reports > "loan activity statement by lender." Already built by Cam — do not create a new one.

**3. Set the filters**
1. Date range from inception (1 July 2021) to the confirmed period end.
2. Select all loan agreement lines.
3. Select the lender contact.
4. Run the report.

> **Watch point:** the saved date range and reporting basis persist as report defaults. The "select all" on loan agreement lines does **not** persist — reapply every time you re-enter the report.

**4. Screen out lenders who don't need a statement** — Review before exporting. Skip if both are true: the loan is fully repaid and closed, and there's been no activity in the last six months.

**5. Export and rename**
5. Export as PDF.
6. Close the report.
7. Copy the lender's name from the report.
8. Rename the file to include the period and the lender name, matching the naming convention used on prior statements in the folder.

> **Do not skip this** — every PDF exports with the same generic filename. Skipping the rename makes the batch unusable.

**6. Draft the email**
9. Open templates in the hello@ inbox.
10. Find "XX, your 31 December 2025 lender activity statement."
11. Clone and edit.

Content pattern: updated cumulative loan count; statement attached; link to current blog post; "follow us on LinkedIn" line with recent borrower progress/latest loans; the approaching AU$4 million deployed milestone; an offer of an accrual version with full principal/interest breakdown on request.

Framing: make lenders feel valued, remind them of impact. For some lenders this is the only LFG email that clears spam filters.

**House register:** Announce, don't recommend or direct — no imperative lending CTAs. Plain Australian English. No bold body copy. No em-dashes.

**7. Send to Cam for sign off** — send the draft email to Cam before anything goes out; he reviews against the December 2025 version. No lender-facing send happens without his sign-off.

**8. Send in batches** — weekly batches rather than one large run, coordinating timing with Renata.

> **Send-from address:** set manually to hello@lendforgood.io at send time on every send — not the default.

### 6. Open decision: cash vs. accrual

| Basis | What it shows | Trade-off |
|---|---|---|
| Cash | Only money that actually moved, by date | Avoids showing invoices raised but not paid. Strips out the principal/interest split and the loan name. |
| Accrual | Splits principal from interest, names the loan, shows default info and final payments | More readable for lenders, but surfaces raised-but-unpaid items. |

Cam set cash as the saved default but is not certain it's right. At least one heavy user has complained the cash view removes detail he relies on and forces him to work out the principal/interest split himself. Escalate to Cam for a decision. Until settled, offering an accrual version on request is the interim mitigation.

### 7. Known issues and improvement notes
- **Fully manual** — every step is hand-run.
- Renata is scoping automated generation via the Xero API, ~USD 50/month, looking for lower-cost alternatives.
- **Lender identification is fragile** — relies on eyeballing the Lender contact group; no filter isolates who needs a statement.
- **No filename automation** — renaming each PDF by hand is the largest time cost in the batch.
- **Reference recording** — Cam ran a Google Meet recording during the 21 July call capturing the Xero screen share; worth pulling if any step is unclear.

### 8. Revision history
| Version | Date | Author | Change |
|---|---|---|---|
| 1.0 | 19 Aug 2026 | Martina Madrid Sebring | Initial draft from Cam's 21 July 2026 walkthrough. Pending Cam sign-off on reporting basis and period end. |

## Next steps
See `20260918_LendForGood_Client_Brief.md` (project root) — P-001 through P-004 in the Problem Register cover the gaps in this SOP.
