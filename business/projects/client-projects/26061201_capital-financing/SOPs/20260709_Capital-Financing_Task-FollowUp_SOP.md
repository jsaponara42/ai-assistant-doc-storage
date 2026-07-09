---
title: "Capital Financing — Follow-Up & Task Management Process (SOP)"
date: 2026-07-09
tags: [client, project, sop]
ai: claude
status: needs-attention
source: 20260709_raw-sop-dictations.md
draft-note: "Built directly from raw dictation, as-is. No clarifying questions were answered — gaps are marked 'Not specified in dictation' rather than assumed. Requires review before treating as a finished SOP."
---

# Capital Financing — Follow-Up & Task Management Process

**Standard Operating Procedure (DRAFT — built from raw dictation)**
Financial Consulting Team — Task & Post-Call Follow-Up

| Field | Value |
| --- | --- |
| Document Owner | Not specified in dictation |
| Department | Financial Consulting |
| Reviewed By | Not specified in dictation |
| Frequency | Ongoing / per-contact |
| Last Updated | July 2026 |

> ⚠️ **This SOP describes a process the speaker identifies as currently broken.** It is documented as-is, including the gaps and inconsistencies described. See the **Breakpoints** section at the end for every place the speaker expressed frustration or a desire for change.

## 1. Purpose

This document captures the current (as described) process by which financial consultants track follow-up tasks in Salesforce and follow up with prospects after strategy and onboarding calls. It is built directly from a dictated walkthrough and is intended to (a) serve as a record of the current process and (b) surface the points where the process is breaking down, as a starting point for automation and correction.

## 2. Background & Key Concepts

**Follow-up tasks in Salesforce:** Financial consultants set tasks for themselves in Salesforce to track follow-ups on accounts/contacts.

**Strategy call / onboarding call:** Two sequential calls held with a prospect (e.g., a referred attorney) — a strategy call, followed by an onboarding call — after which information is sent to the prospect.

**Referenced example case (Audrey Salazar / unnamed attorney):** The attorney was met at a conference in June of a prior year. The strategy call and onboarding call did not happen until January of the following year. Information was sent, but no follow-up occurred afterward. The opportunity was only surfaced again when a different consultant (Brian) met the same attorney at the same conference in June 2026, and the case notes were reviewed — showing the attorney had never been recontacted. The business was lost to a competitor in the interim.

## 3. Roles & Responsibilities (as described)

| Role / Person | Responsibility in This Process |
| --- | --- |
| Financial Consultants (general) | Set follow-up tasks in Salesforce; conduct strategy and onboarding calls; expected to follow up afterward. |
| Audrey Salazar (Financial Consultant) | Referenced by name as an example of a follow-up failure (see Background). |
| Brian (Financial Consultant) | Re-met the same attorney at a later conference; flagged the missed follow-up to the speaker. |
| Speaker / Manager | Reviews accounts/notes when issues surface; identifies the follow-up gap; wants an automated solution. |

## 4. Systems & Tools Used

| Tool | Purpose |
| --- | --- |
| Salesforce | Tasks are created against contact/account profiles for follow-up tracking. Also holds call/contact notes and history. |

## 5. Step-by-Step Process (as currently practiced)

### Step 1: Create a Follow-Up Task
| Field | Detail |
| --- | --- |
| **Inputs** | A contact or account requiring future follow-up. |
| **Where inputs come from** | Interactions with prospects/contacts (calls, meetings, conferences). |
| **Software & tools** | Salesforce |
| **Who is responsible** | Individual financial consultant |
| **Outputs** | A task record attached to the contact or account profile in Salesforce. |
| **Where outputs go** | Stored on the contact/account profile in Salesforce. |
| **Notes (breakpoint)** | ⚠️ Tasks are being created but not consistently cleared or acted on — some remain open on contact/account profiles for months or years. |

### Step 2: Conduct Strategy Call and Onboarding Call
| Field | Detail |
| --- | --- |
| **Inputs** | A qualified prospect (e.g., an attorney met at a conference or through a referral). |
| **Where inputs come from** | Prior contact — e.g., met at a conference, or referred by another consultant. |
| **Software & tools** | Not specified in dictation (calls are described, not the medium — phone/video not stated). |
| **Who is responsible** | Individual financial consultant |
| **Outputs** | Completed strategy call, completed onboarding call, information sent to the prospect. |
| **Where outputs go** | Sent directly to the prospect. Not specified whether/where this is logged in Salesforce. |

### Step 3: Post-Call Follow-Up
| Field | Detail |
| --- | --- |
| **Inputs** | The prospect contacted in Step 2, who has not yet converted to business. |
| **Where inputs come from** | Not specified in dictation — no defined trigger, cadence, or timing is described. |
| **Software & tools** | Not specified in dictation. |
| **Who is responsible** | Individual financial consultant (expected, but described as not happening reliably). |
| **Outputs** | None reliably — this is the step identified as failing. |
| **Where outputs go** | N/A |
| **Notes (breakpoint)** | ⚠️ This step is described as the core failure point: consultants communicate with a prospect once (onboarding call) and then do not follow up. No system currently catches this gap — it was only caught by coincidence in the referenced example case. |

## 6. Desired Future State (stated by speaker, not yet implemented)

The speaker explicitly wants an automated, behind-the-scenes mechanism that follows up (or flags for follow-up) when a contact has had an onboarding or strategy call but no business has been received afterward — removing reliance on individual consultants and "human error."

## 7. Related SOPs & References

Not specified in dictation. Given the process described, related SOPs that may need to be created:
- Salesforce Task Management Standards (how/when tasks should be created and cleared)
- Post-Call Follow-Up Cadence (what follow-up should look like and how often)

## 8. Breakpoints — Frustration & Desired Change

These are the specific points in the dictation where the speaker expressed frustration with the current process or explicitly wanted something changed/automated:

1. **Tasks not being managed.** The speaker does not believe other financial consultants use Salesforce tasks the way they should, and can see tasks sitting open on accounts for months or years without being cleared.
2. **No follow-up after onboarding calls.** General pattern: consultants complete an onboarding call, send information, and never follow up — described as a repeated failure, not a one-off.
3. **The Audrey Salazar / attorney case.** Presented as a concrete, costly example of the above failure — a lost opportunity, discovered only by chance, where the business went to someone else.
4. **"This could have fallen through the cracks."** Direct statement that this is "a problem that we wanna solve for the financial consultants."
5. **Desire to remove human error.** Explicit ask for automation "behind the scenes" to catch cases where no business has resulted after an onboarding/strategy call — so the outcome doesn't depend on an individual consultant remembering to follow up.
