---
title: "Capital Financing — Pre/During/Post Conference Process (SOP)"
date: 2026-07-09
tags: [client, project, sop]
ai: claude
status: needs-attention
source: 20260709_raw-sop-dictations.md
draft-note: "Built directly from raw dictation, as-is. No clarifying questions were answered — gaps are marked 'Not specified in dictation' rather than assumed. Requires review before treating as a finished SOP."
---

# Capital Financing — Pre/During/Post Conference Process

**Standard Operating Procedure (DRAFT — built from raw dictation)**
Business Development / Marketing — Conference Lead Handling

| Field | Value |
| --- | --- |
| Document Owner | Not specified in dictation |
| Department | Business Development / Sales Support |
| Reviewed By | Not specified in dictation |
| Frequency | Per conference |
| Last Updated | July 2026 |

> ⚠️ **This SOP describes a process the speaker identifies as currently broken, slow, and largely manual.** It is documented as-is, including the gaps and inconsistencies described. See the **Breakpoints** section at the end for every place the speaker expressed frustration or a desire for change.

## 1. Purpose

This document captures the current (as described) pre-, during-, and post-conference process: how attendee lists are obtained, imported into Salesforce, matched with email addresses, marketed to, and followed up on. There is currently no defined ROI tracking or goal-setting tied to this process. It is built directly from a dictated walkthrough and is intended to (a) serve as a record of the current process and (b) surface the points where the process is breaking down, as a starting point for automation and correction.

## 2. Background & Key Concepts

**Pre-conference list:** An Excel spreadsheet of expected attendees provided by the conference organizer ahead of the event. It typically does not include email addresses.

**Post-conference list:** A follow-up Excel list of late registrants who were not on the pre-conference list.

**Contact code / conference tagging:** When a contact is imported into Salesforce, they are tagged to the specific conference. This allows the team to see all conferences a given contact has attended, though it does not by itself determine which conference is responsible for closed business.

**CAS:** The current outside Salesforce consultant who performs list imports and deduplication.

**Julius:** An internal person currently handling post-conference email follow-up (templates and cadence set up in Salesforce). Does not make phone calls.

**Outside email-sourcing vendor:** An external source used to find email addresses missing from conference lists. Referred to only as "an outside source" — not specified in dictation.

## 3. Roles & Responsibilities (as described)

| Role / Person | Responsibility in This Process |
| --- | --- |
| Speaker / Manager | Owns the overall process; assigns conference attendees to consultants; reviews performance. |
| CAS (outside Salesforce consultant) | Imports pre- and post-conference Excel lists into Salesforce; deduplicates contacts; tags contacts to the conference. |
| Outside email-sourcing vendor | Provides missing email addresses for contacts without one, based on a list forwarded by the team. |
| Financial Consultants (general, and specifically Victoria Canelli, Audrey Salazar, Brian Gillard) | Assigned attendees to follow up with after the conference — by phone and/or email. |
| Julius | Sends post-conference follow-up emails (templates + cadence in Salesforce) to contacts with email addresses. Does not call. |

## 4. Systems & Tools Used

| Tool | Purpose |
| --- | --- |
| Microsoft Excel | Format in which pre- and post-conference attendee lists are received from conference organizers. |
| Salesforce | System of record for contacts; stores conference tags, email templates, and follow-up cadences. |
| Outside email-sourcing vendor (unspecified) | Used to obtain missing email addresses. |

## 5. Step-by-Step Process (as currently practiced)

### Step 1: Receive Pre-Conference Attendee List
| Field | Detail |
| --- | --- |
| **Inputs** | Attendee list (Excel), provided by the conference. |
| **Where inputs come from** | The conference organizer. |
| **Software & tools** | Microsoft Excel |
| **Who is responsible** | Not specified in dictation (received by the team generally). |
| **Outputs** | Raw Excel attendee list. |
| **Where outputs go** | Passed to CAS for import (Step 2). |
| **Notes (breakpoint)** | ⚠️ The list usually does not include email addresses, which creates downstream problems. |

### Step 2: Import List into Salesforce & Deduplicate
| Field | Detail |
| --- | --- |
| **Inputs** | Raw Excel attendee list from Step 1. |
| **Where inputs come from** | Internal team (forwarded to CAS). |
| **Software & tools** | Salesforce |
| **Who is responsible** | CAS (outside Salesforce consultant) |
| **Outputs** | Contacts created/matched in Salesforce, each tagged to the conference. Existing contacts retain conference history across multiple events. |
| **Where outputs go** | Salesforce contact/account records. |
| **Notes (breakpoint)** | ⚠️ Manual, laborious process. Takes CAS "days" to complete. Deduplication depends on Salesforce's matching criteria — if it doesn't flag a duplicate, CAS can create a second contact record with a separate history, causing downstream confusion. |

### Step 3: Source Missing Email Addresses
| Field | Detail |
| --- | --- |
| **Inputs** | List of contacts imported in Step 2 who do not have an email address on file. |
| **Where inputs come from** | Generated from the Salesforce import (Step 2). |
| **Software & tools** | Not specified in dictation (list is "forwarded" — medium not stated). |
| **Who is responsible** | Internal team forwards the list; an outside vendor sources the emails. |
| **Outputs** | A returned list of email addresses for previously-missing contacts. |
| **Where outputs go** | Forwarded back to CAS for import into Salesforce (Step 2 process, repeated). |
| **Notes (breakpoint)** | ⚠️ Takes "days again." Addresses returned "are not always accurate." Newly-added emails can also trigger automated company emails to contacts who weren't expecting them. |

### Step 4: Pre-Conference Marketing (Templates)
| Field | Detail |
| --- | --- |
| **Inputs** | Salesforce email templates (already created); list of attendees with email addresses. |
| **Where inputs come from** | Salesforce (templates); Steps 2–3 (attendee list with emails). |
| **Software & tools** | Salesforce |
| **Who is responsible** | Not specified in dictation — currently sent manually by the team ("without me having to do it" implies the speaker or their team does this by hand today). |
| **Outputs** | Pre-conference marketing emails sent to attendees already in Salesforce. |
| **Where outputs go** | Sent directly to attendees via Salesforce. |
| **Notes (breakpoint)** | ⚠️ Templates exist but must be sent out manually. There usually isn't enough time to actually premarket before the conference, given how long Steps 2–3 take. |

### Step 5: Receive Post-Conference (Late Registrant) List
| Field | Detail |
| --- | --- |
| **Inputs** | Post-conference attendee list (Excel) of late registrants not on the original pre-conference list. |
| **Where inputs come from** | The conference organizer. |
| **Software & tools** | Microsoft Excel |
| **Who is responsible** | Not specified in dictation. |
| **Outputs** | Additional contacts imported into Salesforce, following the same process as Steps 2–3 (import, dedup, source missing emails). |
| **Where outputs go** | Salesforce. |
| **Notes (breakpoint)** | ⚠️ Same time and accuracy issues as Steps 2–3 repeat here. |

### Step 6: Assign Attendees to Financial Consultants for Follow-Up
| Field | Detail |
| --- | --- |
| **Inputs** | Full list of conference attendees now in Salesforce. |
| **Where inputs come from** | Steps 2, 3, and 5. |
| **Software & tools** | Salesforce |
| **Who is responsible** | Speaker assigns; individual financial consultants execute. |
| **Outputs** | Attendees contacted and followed up with by the assigned consultant. |
| **Where outputs go** | Notes/history logged against the contact (implied, not explicitly stated). |
| **Notes (breakpoint)** | ⚠️ Assignment method is inconsistent: for larger conferences, the consultant(s) who attended get first opportunity on people they personally met, with hundreds of remaining names needing coverage; for smaller conferences, the attending consultant handles follow-up exclusively. Follow-up quality is described as inconsistent — generic emails sent with no phone calls, no urgency, and no true "hunter" business-development approach. Individuals named as underperforming: Victoria Canelli, Audrey Salazar (except for people met in person at the conference), and Brian Gillard (new, limited experience). The speaker states neither Victoria nor Audrey has successfully converted post-conference follow-up into business in three and a half years. |

### Step 7: Back-End Email Follow-Up (Julius)
| Field | Detail |
| --- | --- |
| **Inputs** | Contacts with known email addresses who attended the conference. |
| **Where inputs come from** | Salesforce (post Steps 2–3/5). |
| **Software & tools** | Salesforce (templates and cadence) |
| **Who is responsible** | Julius |
| **Outputs** | Templated follow-up emails sent on a set cadence. |
| **Where outputs go** | Sent directly to contacts via Salesforce. |
| **Notes (breakpoint)** | ⚠️ Entirely manual on Julius's end. Julius only emails — does not call — which limits effectiveness. Separately, consultants are supposed to call the conference/attendee's office to get a phone-listed contact's email address if it's missing, and log it in the system, but this is not being done. |

## 6. Desired Future State (stated by speaker, not yet implemented)

- Automate the pre-conference list import, dedup, and missing-email sourcing so it no longer takes days and doesn't depend on CAS or an outside vendor.
- Automate sending of existing Salesforce templates to attendees pre-conference, without manual effort.
- Build a post-conference "funnel"/drip email campaign (a sequence of targeted marketing emails, not just a single send) — something the team has never done before. The speaker suggests a CMO could help design and implement this as part of a broader campaign strategy.
- Reconsider how attendees are assigned to consultants for follow-up (e.g., by territory or another method), given inconsistent performance.
- Potentially remove Julius's manual role, and/or the reliance on human financial consultants for follow-up, in favor of automation — reducing headcount-driven cost.
- Set actual post-conference goals with sales reps and track ROI per conference, which does not currently exist.

## 7. Related SOPs & References

Not specified in dictation. Given the process described, related SOPs that may need to be created:
- Salesforce Duplicate-Contact Prevention / Matching Criteria
- Conference ROI Tracking & Goal-Setting
- Consultant Territory / Lead Assignment Method

## 8. Breakpoints — Frustration & Desired Change

These are the specific points in the dictation where the speaker expressed frustration with the current process or explicitly wanted something changed/automated:

1. **Missing email addresses on conference lists** — described as creating "a little bit of a problem" that cascades through the rest of the process.
2. **Slow manual import** — CAS "takes days" to import and dedup lists; the speaker calls it "manual" and "laborious."
3. **Duplicate contact risk** — if Salesforce doesn't flag a duplicate by its own criteria, CAS can create a second, disconnected contact history — described as "creates problems for everybody."
4. **Slow, unreliable email sourcing** — the outside vendor also "takes days again," and results "are not always accurate."
5. **No time to premarket** — by the time the list/email process finishes, there usually isn't time left to actually market before the conference.
6. **Manual sending of existing templates** — templates already exist in Salesforce but must be sent manually; explicit wish: "would be nice to automate this... without me having to do it."
7. **Same delays repeat post-conference** for the late-registrant list.
8. **Inconsistent, low-urgency follow-up by consultants** — described as sending generic ("bogey") emails, not calling, "not showing any signs of urgency."
9. **Named performance concerns** — explicit, specific frustration with Victoria Canelli and Audrey Salazar (three and a half years, no successful post-conference conversions), and concern about Brian Gillard's limited follow-up as a newer employee.
10. **Julius is email-only** — "he does not jump on a phone, so he is limited," even though he's doing more than some consultants.
11. **Consultants not calling offices for missing emails** — explicitly asked of them, explicitly not being done.
12. **Desire to reassign or remove people from the process** — "if we can take out the element of them doing the work because they're not successful, obviously, we can remove them altogether."
13. **No ROI tracking or post-conference goals exist today** — flagged as a gap the speaker wants addressed.
14. **Explicit ask for a post-conference drip/funnel campaign** — something never built before, that the speaker is excited about and wants to know if it's possible.
15. **Desire to remove manual dependency on Julius and/or CAS entirely** — "do we take out the element of Julius altogether that's manual... and have this all automated going forward and remove the cost of an employee doing this for us."
