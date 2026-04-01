# Cause Crazy — Lead Magnet & ICP/AdWords Automation
## Standard Operating Procedure

**Client:** Rocky Fisher / Cause Crazy
**Prepared by:** Blue Tusk
**Version:** 1.0
**Date Created:** April 1, 2026

---

## 1. Purpose (Plain Language)

This document explains how two connected automations work together to handle new leads for Cause Crazy — from the moment someone fills out a form, through the delivery of a Purpose Pathway document, and all the way to when a lead becomes a paying customer and receives a custom ICP and AdWords strategy.

You do not need to be technical to follow this SOP. It explains what happens automatically, what requires a human action, and what you must never change without involving the automation owner (Blue Tusk).

---

## 2. Who This Is For

- Rocky Fisher and any Cause Crazy team member who manages leads or contacts in Zoho CRM
- Operations staff who may assist with monitoring the process
- Anyone who needs to understand what the automations do and how to avoid breaking them

---

## 3. Tools and Access Required

| Tool | Role in This Process |
|---|---|
| **JotForm** | Lead intake form (Purpose Pathway form). Collects lead information and triggers the first automation. |
| **Make.com** | The automation platform. Runs both workflows: Lead Magnet creation and ICP/AdWords creation. |
| **OpenAI API** | Generates the Purpose Pathway document content. Connected under the Cause Crazy account. |
| **Google Drive** | Stores all generated documents in a shared drive. Folder name: `causecrazyaiautomation` (shared with Blue Tusk). |
| **Zoho CRM** | Manages leads and contacts. Stores share links for generated documents. Account: `jotform@causecrazy.com` |
| **Email (jotform@causecrazy.com)** | Sends the Purpose Pathway email to the lead two business days after form submission. |

---

## 4. Files and Folders Used

| Item                                | Description                                                                                                                                                                                                   |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Master Folder (Google Drive)**    | `Cause Crazy AI Automations with Blue Tusk` (https://drive.google.com/drive/folders/186d0v4DDA70zBl94wjTGiNasLZRjaJGD?usp=sharing) — shared between Cause Crazy and Blue Tusk. All generated files live here. |
| **01-Leads subfolder**              | Inside the master folder. One subfolder is created here for each new lead. Contains their Purpose Pathway document.                                                                                           |
| **02-ICP + AdWords Docs subfolder** | Inside the master folder. One subfolder is created here for each converted contact. Contains their ICP and AdWords documents.                                                                                 |
| **Purpose Pathway Cover Page**      | A cover page file in the master folder (`Cause Crazy AI Automations with Blue Tusk`). Must always exist here — it is pulled in every time a Purpose Pathway is created.                                       |

> ⚠️ **CRITICAL:** The Google Drive folder structure above must not be changed, renamed, or moved. The Purpose Pathway Cover Page file must remain in the master folder at all times. If any folder or file needs to change, contact Blue Tusk first.

---

## 5. Before You Start — Checklist

Before using or monitoring this system, confirm the following:

- [ ] You have access to Zoho CRM using the `jotform@causecrazy.com` account
- [ ] The Google Drive shared folder `Cause Crazy AI Automations with Blue Tusk` (https://drive.google.com/drive/folders/186d0v4DDA70zBl94wjTGiNasLZRjaJGD?usp=sharing) is visible and accessible
- [ ] The Purpose Pathway Cover Page file exists inside the master folder
- [ ] You know who to contact (Blue Tusk - John-Carlos Saponara) if something looks wrong

---

## 6. Step-by-Step Procedure

### Phase A: Lead Magnet Flow (Triggered by JotForm Submission)

| # | Action | Who / System | Expected Result |
|---|---|---|---|
| 1 | A potential lead fills out the Purpose Pathway JotForm on the Cause Crazy website. | Lead (self-service) | Form submission is received by JotForm. |
| 2 | JotForm triggers the Make.com automation called **Cause Lead Magnet JotForm**. | Automatic (Make.com) | Make.com begins processing the submission. |
| 3 | Make.com checks Zoho CRM for an existing lead with the same email address. | Automatic (Make.com + Zoho) | Match found: existing lead is updated. No match: a new lead record is created in Zoho. |
| 4 | Make.com uses the OpenAI API (Cause Crazy account) to generate a Purpose Pathway document based on the lead's form responses. The Purpose Pathway Cover Page is pulled from the master Google Drive folder and included. | Automatic (OpenAI API) | Purpose Pathway document is created. |
| 5 | A new subfolder for this lead is created inside the **01 Leads** folder in Google Drive. The Purpose Pathway document is saved there. | Automatic (Make.com) | Lead's folder is created and document is saved. |
| 6 | The folder's share link is generated and added to the lead's record in Zoho CRM. | Automatic (Make.com + Zoho) | The lead record in Zoho now shows a link to the lead's Google Drive folder. |
| 7 | Make.com waits two full business days. | Automatic (Make.com — timed delay) | System is paused for two business days. |
| 8 | A partial version of the Purpose Pathway is emailed to the lead from `jotform@causecrazy.com`. The email is designed to encourage the lead to schedule a sales meeting with Rocky. | Automatic (Make.com via jotform@causecrazy.com) | Lead receives the email. The goal is for them to book a meeting with Rocky. |

---

### Phase B: ICP and AdWords Flow (Triggered by Lead Conversion in Zoho)

This phase begins only when a human takes an action in Zoho CRM. The full Purpose Pathway is presented by Rocky in the sales meeting. If the lead agrees to move forward:

| #   | Action                                                                                                                                                                                  | Who / System                                            | Expected Result                                                              |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------- | ---------------------------------------------------------------------------- |
| 9   | Rocky (or a team member) opens the lead's record in Zoho CRM and clicks the **Convert** button. This changes the lead into a contact.                                                   | Rocky / Cause Crazy team member (manual action in Zoho) | Lead record is converted to a Contact in Zoho.                               |
| 10  | Zoho automatically fires a webhook (a notification trigger) that starts the Make.com automation called **ICP and AdWords Creation Zoho Trigger**.                                       | Automatic (Zoho webhook)                                | Make.com receives the contact's email and Zoho Contact ID.                   |
| 11  | Make.com searches Google Drive for the contact's Purpose Pathway folder (from Phase A) and downloads the Purpose Pathway document.                                                      | Automatic (Make.com)                                    | The Purpose Pathway document is found and downloaded.                        |
| 12  | Make.com uses the OpenAI API to write two new documents: an **ICP (Ideal Customer Profile) document** and a **Google AdWords strategy document**, based on the Purpose Pathway content. | Automatic (OpenAI API)                                  | Two new documents are created.                                               |
| 13  | A new subfolder for this contact is created inside the **02 ICP + AdWords Docs** folder in Google Drive. Both documents are saved there.                                                | Automatic (Make.com)                                    | Subfolder created and documents saved.                                       |
| 14  | The share link for the new folder is generated and added to the contact's record in Zoho CRM.                                                                                           | Automatic (Make.com + Zoho)                             | The contact record in Zoho now shows a link to their ICP and AdWords folder. |

---

## 7. How the Pieces Connect (System Flow)

| Step / Tool | | Passes To |
|---|---|---|
| JotForm (form submitted) | → | Make.com (Cause Lead Magnet flow starts) |
| Make.com | → | Zoho CRM (create or update lead record) |
| Make.com + OpenAI API | → | Google Drive (Purpose Pathway saved in 01 Leads folder) |
| Google Drive | → | Zoho CRM (share link stored on lead record) |
| Make.com (2-day delay) | → | Email sent to lead from jotform@causecrazy.com |
| Rocky clicks Convert in Zoho | → | Zoho webhook fires to Make.com (ICP/AdWords flow starts) |
| Make.com downloads Purpose Pathway | → | OpenAI API writes ICP + AdWords documents |
| Make.com + OpenAI API | → | Google Drive (documents saved in 02 ICP and AdWords Docs folder) |
| Google Drive | → | Zoho CRM (share link stored on contact record) |

---

## 8. Quality Checks and Success Criteria

After a JotForm is submitted, verify:

- [ ] A new lead record (or updated record) appears in Zoho CRM within a few minutes
- [ ] The lead record in Zoho shows a Google Drive share link in the appropriate field
- [ ] A new subfolder for the lead exists inside `Cause Crazy AI Automations with Blue Tusk` (https://drive.google.com/drive/folders/186d0v4DDA70zBl94wjTGiNasLZRjaJGD?usp=sharing)  > 01-Leads`
- [ ] The lead receives an email two business days after form submission

After a lead is converted to a contact in Zoho, verify:

- [ ] A new subfolder for the contact exists inside `Cause Crazy AI Automations with Blue Tusk` > 02-ICP + AdWords Docs`
- [ ] The contact record in Zoho shows a Google Drive share link for the ICP/AdWords folder
- [ ] Both the ICP document and the AdWords document appear in the contact's subfolder

---

## 9. Common Issues and Fixes

| Problem                                                 | Likely Cause                                                                                                           | What to Do                                                                                                                                                                                              |
| ------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Lead record not created in Zoho after form submission   | Make.com connection to Zoho may have broken, or Zoho access was changed                                                | Contact Blue Tusk immediately. Do not attempt to fix in Make.com.                                                                                                                                       |
| Purpose Pathway document not generated                  | OpenAI API key may have expired, or the Cover Page file is missing from the master folder                              | Check that the Cover Page file exists in the master folder. If yes, contact Blue Tusk.                                                                                                                  |
| Lead did not receive email after two days               | The `jotform@causecrazy.com` email account may have a problem, or the Make.com automation failed                       | Check the email account is active. Check `jotform@causecrazy.com` "Sent" emails for an email that matches the email address the lead submitted the form with. Contact Blue Tusk if the account is fine. |
| ICP/AdWords docs not created after converting a contact | Zoho webhook may not have fired, or Make.com flow failed. Often caused by a change to Zoho access or folder structure. | Contact Blue Tusk. Do not click Convert again on the same record.                                                                                                                                       |
| Google Drive link not appearing on Zoho record          | Make.com step that writes the link may have failed                                                                     | Check the Google Drive folder for the document. If it exists, contact Blue Tusk to fix the Zoho link write step.                                                                                        |

---

## 10. Critical Dependencies and Change Warnings

> ⚠️ **CRITICAL — DO NOT CHANGE WITHOUT APPROVAL FROM BLUE TUSK**
>
> The following items keep both automations working. Changing any of them without first contacting Blue Tusk **will break the automation.**

1. **OpenAI API Keys** — Stored under the Cause Crazy account. If they expire, are revoked, or are changed, document generation will stop. Do not rotate or change these keys without Blue Tusk's involvement.

2. **Google Drive Folder Structure** — The folder `causecrazyaiautomation` and its two subfolders (`01 Leads`, `02 ICP and AdWords Docs`) must remain exactly as they are. Do not rename, move, or delete any folder.

3. **Purpose Pathway Cover Page** — This file must always exist inside the master Google Drive folder. Do not delete or move it.

4. **Zoho CRM Access (jotform@causecrazy.com)** — Make.com connects to Zoho using this account. Any change to this account's permissions, password, or access will break both automations.

5. **Zoho Webhook** — A webhook inside Zoho triggers the ICP/AdWords flow when a lead is converted. Do not delete or modify this webhook. If Zoho is reconfigured, contact Blue Tusk first.

6. **Email Account (jotform@causecrazy.com)** — The two-day follow-up email is sent through this account. If this account is changed, suspended, or its password is updated, the email step will fail.

**Safe-change procedure:** If any of the above items must change, notify Blue Tusk before making the change. Blue Tusk will update the automation connections and test them before the change goes live.

---

## 11. Change Log and Ownership

| Field | Value |
|---|---|
| **Automation Owner** | Blue Tusk (John-Carlos) |
| **Client** | Rocky Fisher / Cause Crazy |
| **Zoho Account Used** | jotform@causecrazy.com |
| **Make.com Flows** | Cause Lead Magnet JotForm · ICP and AdWords Creation Zoho Trigger |
| **Google Drive Shared Folder** | causecrazyaiautomation (shared between Cause Crazy and Blue Tusk) |
| **Document Version** | 1.0 |
| **Date Created** | April 1, 2026 |
| **Last Updated** | April 1, 2026 |

To request changes or report issues, contact Blue Tusk directly. Do not attempt to modify Make.com flows, Zoho webhooks, or Google Drive folder structures without Blue Tusk's involvement.
