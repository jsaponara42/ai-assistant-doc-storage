---
title: "Notion Build Spec — Operating System Sandbox (Phases 1–3)"
date: 2026-10-08
tags: [project, tool, ai]
ai: claude
status: needs-attention
---

# Notion Build Spec: Operating System Sandbox

## Summary
A build spec for **Notion AI** to build the Notion half of the AI-native operating architecture in JC's own workspace, as a **sandbox with example data**. It covers only what Notion can build natively: databases, properties, relations, page templates, views and seed pages. It's built in three phases; **build one phase at a time**. Migration of JC's active work comes later, with its own spec.

## Context
- Source design: [[business/projects/internal/product/20261008_ai-native-operating-architecture]] (Sections 3, 4, 10, 12). Decisions: [[business/projects/internal/product/20261008_ai-native-architecture-decision-log]].
- **How to use this file:** paste the **Opening prompt** plus **Global rules** plus the **one phase** you want built into Notion AI. Don't paste all phases at once.
- After each phase, check it against that phase's **Done when** list before starting the next.

---

## Content

### Opening prompt (paste first)

> You're building the Notion workspace for a small firm's AI-native operating system. Build it as a **sandbox** inside a new top-level page called **"Operating System (Sandbox)"** in my workspace. Follow the spec below exactly. Build **only the phase I give you**. Use the exact database names, property names, property types and select options listed. Every property gets the description given. If something in the spec isn't possible in Notion (for example, grouping a view by a rollup), **don't improvise silently**: build the closest alternative and list what you changed at the end. When you're done, give me a list of every database you created with its link, and every view and template, so I can record them in the System Registry. Mark all example data clearly with "EXAMPLE" so it can be deleted later.

### Global rules (paste with every phase)

1. **Names are exact.** Use the database and property names as written. Don't add databases or properties that aren't in the spec.
2. **Select values are lowercase,** exactly as listed.
3. **Every property gets its description** (the text after the dash in each table).
4. **Every relation is two-way,** with both sides named as listed.
5. **Every database has these standard properties:**
   - **Summary** (Text): One line describing the current state of this item. Kept current; agents read this instead of opening the page.
   - **Needs Attention** (Checkbox): Checked when a person needs to look at this item.
   - **Created** (Created time): Set automatically. Never edit.
   - **Last Edited** (Last edited time): Set automatically. Never edit.
6. **No orphan pages.** Every content page is a row in a database. The only free-standing pages are the top-level page, Home, Clients, and the person home template.
7. **Archive with a status, never by deleting.** Default views hide archived rows.
8. **Titles are clean human titles** with no dates or IDs in them (dates and IDs live in properties).
9. **Client codes** are 3 capital letters (e.g. `ACM`). **Project IDs** use the format `{CLIENT}-{YYMMDDNN}` (e.g. `ACM-26100101`): client code, then the date the project was opened as YYMMDD, then a two-digit sequence for that day. Assigned once, never changed.

---

### Phase 1: Foundations

**Build:** Companies, People, Projects, Tasks, Knowledge; the Home page, Clients page, person home template; the System Registry and quick reference pages; example data.

#### 1.1 Companies
Clients, partners and vendors. Base client context lives on the page.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Company name. |
| Client Code | Text | 3 capital letters | Unique 3-letter code used in every project ID. Never changed or reused. |
| Type | Select | client, partner, vendor, internal | What kind of company this is. |
| Status | Select | active, paused, past, archived | Current relationship status. |
| People | Relation → People | two-way; other side "Company" | Contacts who work at this company. |
| Projects | Relation → Projects | two-way; other side "Company" | All projects for this company. |
| Drive Folder | URL | | Link to this company's client folder in Google Drive. |
| AI Rules | Text | | Any restrictions on how AI may use this client's information. Read before every task. |
| Owner | Person | | Team member responsible for the relationship. |
| + standard properties | | | |

**Page template ("Company"):** headings in this order: **Overview**, **People and roles**, **Scope history**, **Tools they use**, **AI rules**, **Preferences**, **History**. Then a linked view: **Projects** (this company's projects; table; sorted by Stage, then Last Edited newest first; hide archived).

#### 1.2 People
Client-side and external contacts only. Team members are Notion users, not rows here.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Person's full name. |
| Company | Relation → Companies | (other side of Companies.People) | The company this person works for. Leave empty for early prospects. |
| Email | Email | | Primary email. |
| Phone | Phone | | Primary phone. |
| Title | Text | | Job title. |
| LinkedIn | URL | | LinkedIn profile. |
| Relationship Stage | Select | identified, reached out, in conversation, opportunity, client, past client, dormant | Where this relationship stands. Drives the pipeline board. |
| Last Contacted | Date | | Date of the most recent email or meeting. Will be set by a script; set by hand until then. |
| Next Follow-up | Date | | When to reach out next. |
| Last Talked About | Text | | One line on the most recent substantive conversation. |
| Source | Select | referral, outreach, event, inbound, network | How this relationship started. |
| + standard properties | | | |

The reverse sides of the Projects contact-role relations (Main Contact For, Secondary Contact For, Decision Maker For, Stakeholder For) also appear here once Projects is built.

**Page template ("Person"):** headings: **About**, **Touchpoints**. Under Touchpoints, a note: *"Append-only log, newest at the bottom. One line each: date — what happened — source (human / ai). Only important things: first meetings, intros, pricing or scope talks, contract events, personal details, complaints. Project-specific conversation goes on the project, not here."*

#### 1.3 Projects
Every unit of scoped work: client, internal and admin. Project context lives on the page.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Clean project name (no ID or date). |
| Project ID | Text | `{CLIENT}-{YYMMDDNN}` | Permanent project ID. Assigned once at creation, never changed. Used in Drive folder names and file names. |
| Area | Select | client, internal, admin | Which part of the business this project belongs to. |
| Company | Relation → Companies | (other side of Companies.Projects) | The client or company this project is for. Internal and admin projects relate to the firm's own company row. |
| Stage | Select | discovery, proposal, signed, active, ongoing, done, lost, archived | Where the project stands. "ongoing" is for evergreen projects with no end date. |
| Main Contact | Relation → People | two-way; other side "Main Contact For" | Main client-side contact for this project. |
| Secondary Contact | Relation → People | two-way; other side "Secondary Contact For" | Backup client-side contact. |
| Decision Maker | Relation → People | two-way; other side "Decision Maker For" | Who signs off on this project. |
| Stakeholders | Relation → People | two-way; other side "Stakeholder For" | Other people with a stake in this project. |
| Owner | Person | | Team member who owns delivery. |
| Start Date | Date | | When work started. |
| Target End | Date | | Planned end date. Empty for ongoing projects. |
| Drive Folder | URL | | Link to this project's folder in Google Drive. |
| Tasks | Relation → Tasks | two-way; other side "Project" | Tasks under this project. |
| + standard properties | | | |

**Page template ("Project")** — this page works like a folder. In this order:
1. A callout at the top: **"Drive folder:"** followed by the Drive Folder link, and **"Project ID:"** followed by the Project ID.
2. Heading **Where things stand**, with three sub-headings: **Current state**, **Open items**, **Watch items**. A note under it: *"Rewritten at the end of each working session. Keep it short."*
3. Heading **Scope**.
4. Heading **Decisions** (dated bullets, newest at the bottom).
5. Heading **Tasks**: linked view of Tasks filtered to this project, Status is not done/cancelled, sorted by Due.
6. (Phase 2 adds Drafts, Meetings and Handoffs views here.)

#### 1.4 Tasks

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | What needs doing, as an action. |
| Project | Relation → Projects | (other side of Projects.Tasks) | The project this task belongs to. |
| Owner | Person | team members only | Who is doing it. |
| Due | Date | | When it's due. |
| Status | Select | to do, doing, waiting, done, cancelled | Current state of the task. |
| Priority | Select | high, medium, low | How important it is. |
| + standard properties | | | |

#### 1.5 Knowledge
Company-level living knowledge: SOPs, guides, training, policies, the quick reference and the System Registry.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Title of the knowledge page. |
| Type | Select | sop, guide, template-instructions, policy, training, quick-reference, system | What kind of knowledge this is. "system" pages make up the System Registry. |
| Department | Select | operations, delivery, sales, finance, hr, admin | Which part of the business it covers. |
| Audience | Select | everyone, team, admins | Who should read it. |
| Owner | Person | | Who keeps it current. |
| Status | Select | draft, active, needs-review, archived | Whether it's current. |
| Last Reviewed | Date | | When someone last confirmed it's accurate. |
| Drive Template | URL | | Link to a blank formatted template in Drive, if this page explains one. |
| AI | Select | human, claude, notion-ai | Who wrote it. |
| Tags | Multi-select | (start empty) | Free tags. |
| + standard properties | | | |

**Seed pages (create these as Knowledge rows):**
- **"System Registry"** (Type = system, Audience = admins). Body:
  - **Database index:** a table with columns Database, Purpose, Owner, Core (yes/no), Locked (yes/no), Link. One row per database built.
  - **Relationships:** a table with columns From, To, Property (from side), Property (to side), Why. Fill it from this spec.
  - **Change protocol:** paste the eight rules under "Change protocol text" below.
  - **Standard views:** a list of every view built, with its database, filter, sort and grouping.
- **One "Registry: {Database}" page per database** (Type = system), each with: Purpose, Owner and approvers, Who writes / who reads, AI access, Sensitivity, Key properties, Relations, Skills and views that depend on it, Core (yes), Lock status (unlocked until reviewed).
- **"How to use this system"** (Type = quick-reference, Audience = everyone, Status = draft). Draft it from the **Quick reference outline** below.
- **"Getting started"** (Type = training, Audience = everyone, Status = draft). Short: what the system is for, the Home page, your own page, where to ask questions.

**Change protocol text:**
1. Add a property before adding a database. A new database only when lifecycle, permissions or cardinality differ; a filtered subset is a view.
2. Don't rename or delete properties or select options. Add, deprecate and migrate instead.
3. Every relation is two-way, named on both sides, with its reason recorded.
4. Every property gets a description. Select values are lowercase.
5. Try changes in a scratch copy first.
6. Order of work: registry → schema → skills → backup manifest → views and templates → quick reference and training.
7. Anything involving money, legal, HR or client confidentiality starts in a restricted teamspace.
8. Log every change: date, what, why, who approved.

**Quick reference outline ("How to use this system"):**
1. **Where things live:** Notion = drafts, context, people, projects, tasks, knowledge. Google Drive = finals and files clients receive. Gamma = presentations. Billing tool = money.
2. **How to find anything:** start at Home; Clients → company → project; every project page has its tasks, drafts, meetings and handoffs.
3. **Tip: find by ID.** Type a client code (`ACM`) or project ID (`ACM-26100101`) into search or a view filter to jump straight to that client's or project's work.
4. **Naming in one line each:** titles are clean; project IDs are `{CLIENT}-{YYMMDDNN}`; internal Drive files start `YYYYMMDD_{ID}_`; client-facing files get clean titles.
5. **Keep Summary current** and tick Needs Attention when someone needs to look.
6. **What AI will and won't do:** drafts and prepares; never sends to clients, never touches money, never publishes, never changes the system without approval.
7. **Start and end a session:** start by reading the project's "Where things stand"; end by writing a Handoff and updating "Where things stand" (Phase 2).
8. **Need a change?** Ask the system owner; changes follow the change protocol in the System Registry.

#### 1.6 Pages and views

**Home** (free-standing page under the top-level page). Linked views only, in this order:
1. **Needs attention — projects:** Projects where Needs Attention is checked.
2. **Needs attention — tasks:** Tasks where Needs Attention is checked, or Due is on or before today and Status is not done/cancelled.
3. **This week:** Tasks due in the next 7 days, Status not done/cancelled, sorted by Due.
4. **Follow-ups due:** People where Next Follow-up is on or before today.
5. **Pipeline:** board of People grouped by Relationship Stage (hide client, past client, dormant).
6. **Active projects:** Projects where Stage is discovery, proposal, signed, active or ongoing, sorted by Last Edited newest first.
7. Links to **Clients**, **Knowledge**, **How to use this system**.

**Clients** (free-standing page). Linked views:
1. **By client:** Projects table, filter Area = client, **grouped by Company**, sorted by Stage. Archived and done projects hidden by default.
2. **Companies:** Companies table, filter Status = active.

**Person home template** ("My page"): a page template anyone can duplicate, with linked views filtered to **Me**:
1. **My tasks:** Tasks where Owner is Me, Status not done/cancelled, sorted by Due.
2. **My projects:** Projects where Owner is Me, not archived/done.
3. **My attention items:** Tasks where Owner is Me and Needs Attention is checked.
4. Heading **Private notes**.
(Phase 2 adds My drafts and My meetings.)

**Default views on each database:** a main table hiding archived rows; Knowledge also gets a view grouped by Type.

#### 1.7 Example data (all marked EXAMPLE)
- **Companies:**
  - "EXAMPLE Blue Tusk" — Client Code `BTK`, Type internal, Status active.
  - "EXAMPLE Acme Advisory" — `ACM`, client, active.
  - "EXAMPLE Oakridge Logistics" — `OAK`, client, active.
- **People:** two per client company (one with Relationship Stage = client), plus two prospects with no company (Stage = reached out and in conversation; one with Next Follow-up in the past).
- **Projects:**
  - "EXAMPLE Discovery and Roadmap" — `ACM-26100101`, Area client, Company Acme, Stage done.
  - "EXAMPLE Operations Build" — `ACM-26100201`, client, Acme, active, with Main Contact and Decision Maker set.
  - "EXAMPLE Logistics Proposal" — `OAK-26100501`, client, Oakridge, proposal.
  - "EXAMPLE Outreach Q4" — `BTK-26100801`, internal, Blue Tusk, ongoing.
  - "EXAMPLE Finance and Admin" — `BTK-26100802`, admin, Blue Tusk, ongoing.
- **Tasks:** 6–8 across the projects, with a mix of statuses, one overdue, one with Needs Attention checked.
- Fill **Summary** on every example row and **Where things stand** on the active project.

#### Phase 1 done when
- [ ] Five databases exist with exactly the listed properties, types, options and descriptions.
- [ ] All relations are two-way and named on both sides (including the four contact roles).
- [ ] Company, Person and Project templates exist and are the defaults.
- [ ] Home, Clients and the person home template work with the example data.
- [ ] System Registry, one registry page per database, "How to use this system" and "Getting started" exist.
- [ ] Notion AI has listed any spec item it couldn't build exactly.

---

### Phase 2: Working layer

**Build:** AI Drafts, Meeting Notes, Handoffs; add their views to the Project template, Home, person home template; the "All work" view; registry pages; example data.

#### 2.1 AI Drafts
All drafts of all documents. Notion is always drafts; finals live in Google Drive or Gamma.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Clean human title, the same title the final will have. |
| Project | Relation → Projects | two-way; other side "Drafts" | The project this draft belongs to. |
| Project ID | Rollup | Project → Project ID | Project ID, pulled from the project. |
| Client Code | Formula or rollup | first 3 characters of Project ID | Client code, used to group drafts by client. |
| Drive Folder | Rollup | Project → Drive Folder | Where the final will go. |
| Type | Select | document, email, proposal, sop, report, deck-outline, sheet, post, other | What kind of draft this is. |
| Audience | Select | internal, client | Who will receive the final. Sets how the final file is named. |
| Status | Select | draft, in progress, sent, published, archived | draft = in Notion; in progress = Google file exists but isn't final; sent / published = delivered. |
| Destination | Select | google-drive, gamma, client-workspace, email, notion | Where the final will live. |
| Final Link | URL | | Link to the final file once it exists. |
| AI | Select | human, claude, notion-ai | Who wrote the draft. |
| Tags | Multi-select | (start empty) | Free tags. |
| + standard properties | | | |

#### 2.2 Meeting Notes
Meeting close-outs: summary, decisions and commitments.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Meeting name. |
| Date | Date | | When the meeting happened. |
| Project | Relation → Projects | two-way; other side "Meeting Notes" | The project this meeting was about. |
| Attendees | Relation → People | two-way; other side "Meetings" | External attendees. |
| Team Attendees | Person | | Team members who attended. |
| Meeting Type | Select | client, prospect, internal, partner | What kind of meeting. |
| Source | URL | | Link to the transcript or recording. |
| AI | Select | human, claude, notion-ai | Who wrote the close-out. |
| + standard properties | | | |

**Page template ("Meeting close-out"):** headings: **Summary**, **Decisions**, **Commitments** (each becomes a Task), **Notes**.

#### 2.3 Handoffs
One row per working session. **Append-only timeline: rows are never edited after creation.**

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Short label, e.g. "Build plan drafted". |
| Projects | Relation → Projects | two-way; other side "Handoffs"; allow multiple | Projects this session touched. |
| Written By | Select | human, claude, notion-ai | Who wrote this handoff. Needed because agent edits show under the connected person's name. |
| Author | Person | | The person who ran the session. |
| Created By | Created by | | Set automatically. |
| + standard properties | | | |

**Page template ("Handoff"):** headings: **Done**, **Open**, **Next**.

#### 2.4 View additions
- **Project template:** add under the Tasks view, each sorted by Last Edited newest first:
  - **Drafts:** AI Drafts for this project, not archived.
  - **Meetings:** Meeting Notes for this project, sorted by Date newest first.
  - **Handoffs:** Handoffs for this project, newest first, last 10.
- **All work** (new free-standing page, linked from Home): AI Drafts table **grouped by Client Code**, then sorted by Project ID and Last Edited. Archived hidden. Also a board version grouped by Client Code with sub-groups by Project ID, if Notion supports it. *If grouping by a formula or rollup isn't supported, say so and propose the closest alternative.*
- **Home:** add **Recent drafts** (AI Drafts edited in the last 7 days) and **Needs attention — drafts**.
- **Person home template:** add **My drafts** (AI Drafts where Created By is Me, not archived) and **My meetings** (Meeting Notes where Team Attendees contains Me, last 14 days).
- **A stale-drafts view** on AI Drafts: Status = draft and Last Edited more than 30 days ago.

#### 2.5 Registry and quick reference
- Add "Registry: AI Drafts", "Registry: Meeting Notes", "Registry: Handoffs" pages; add the three databases to the System Registry index and relationships tables; add the new views to Standard views.
- Update "How to use this system" point 7 (start and end a session) now that Handoffs exist.

#### 2.6 Example data (marked EXAMPLE)
- 4–6 drafts across the example projects: mixed Types, Audience, Status; one published with a placeholder Final Link; one stale.
- 2–3 meeting notes on "EXAMPLE Operations Build" with attendees, decisions and commitments, and matching Tasks.
- 2 handoffs on "EXAMPLE Operations Build", one written by human, one by claude.

#### Phase 2 done when
- [ ] Three databases exist exactly as listed; rollups and the Client Code formula work.
- [ ] The Project template shows Tasks, Drafts, Meetings and Handoffs for the right project only.
- [ ] "All work" groups drafts by client (or the agreed alternative).
- [ ] Home and the person home template show the new views.
- [ ] Registry and quick reference are updated.

---

### Phase 3: Registers (build only when asked)

**Build:** Documents; Contracts and Invoices in a **restricted teamspace** (or restricted pages if the plan has no teamspace permissions).

#### 3.1 Documents
Register of files clients send. Originals live in Drive.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Original file name. |
| Project | Relation → Projects | two-way; other side "Documents" | Project the file belongs to. |
| Company | Relation → Companies | two-way; other side "Documents" | Company that sent it. |
| Sender | Relation → People | two-way; other side "Documents Sent" | Who sent it. |
| Received | Date | | When it arrived. |
| Drive Link | URL | | Link to the original in Drive. |
| Key Facts | Text | | The important facts from the file, so it doesn't need re-reading. |
| Status | Select | new, processed, needs action, archived | Processing state. |
| AI Access | Select | allowed, restricted | Whether AI may read the file. Restricted files get a human-written summary. |
| + standard properties | | | |

Add a **Documents** linked view to the Project template.

#### 3.2 Contracts (restricted)

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Contract name. |
| Type | Select | msa, sow, nda, amendment, other | Contract type. |
| Company | Relation → Companies | two-way; other side "Contracts" | Counterparty. An MSA relates to the company. |
| Project | Relation → Projects | two-way; other side "Contracts" | A SOW relates to its project. |
| Parent Contract | Relation → Contracts | self-relation; other side "Child Contracts" | A SOW's MSA. |
| Status | Select | draft, sent, signed, active, expired, terminated | Contract state. |
| Signed Date | Date | | When it was signed. |
| Term End | Date | | When it ends. |
| Renewal Date | Date | | When it renews or needs a decision. |
| Value | Number | currency | Contract value. |
| Drive Link | URL | | Link to the signed PDF. |
| + standard properties | | | |

Views: unsigned, active, renewing in 90 days, by company.

#### 3.3 Invoices (restricted)
The billing tool is the source of truth; this is the register. **Paid status and amounts are written only by scripts, never by people's AI agents.**

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Invoice number. |
| External ID | Text | | The invoice's ID in the billing tool. |
| Billing System | Select | stripe, quickbooks, wise, other | Which tool issued it. |
| Project | Relation → Projects | two-way; other side "Invoices" | Project billed. |
| Company | Relation → Companies | two-way; other side "Invoices" | Company billed. |
| Amount | Number | currency | Invoice amount. Set by script. |
| Issued | Date | | Issue date. |
| Due | Date | | Due date. |
| Status | Select | draft, sent, paid, overdue, void | Payment status. Set by script. |
| Paid Date | Date | | When it was paid. Set by script. |
| Link | URL | | Link to the invoice in the billing tool. |
| + standard properties | | | |

Views: unpaid, overdue, paid this month. Add restricted linked views of "Unpaid invoices" and "Contracts renewing" to an admin-only section of Home.

#### Phase 3 done when
- [ ] Documents exists and appears on the Project template.
- [ ] Contracts and Invoices exist in a restricted area that a non-admin can't open.
- [ ] Registry pages and the quick reference are updated.

---

### Out of scope for Notion AI (don't build)
- **Google Drive folders,** INDEX and CONVENTIONS (built separately; Notion stores links only).
- **Scripts:** backups, Last Contacted updater, payment webhooks, reconciliation, drift checks.
- **The skills repo** and skill deployment.
- **Database locks:** JC applies them by hand after reviewing each phase.
- **Migration of real data:** a separate spec after the sandbox is approved.

## Next steps
- [ ] JC: run Phase 1 in Notion AI; check the "done when" list; note anything it changed.
- [ ] Record the database links Notion AI returns in the System Registry page (and later in the skills' config).
- [ ] Run Phase 2, then review the "All work" grouping result.
- [ ] After review: lock core databases by hand; decide whether Phase 3 runs in the sandbox.
- [ ] Write the migration spec for JC's active work (contacts, projects, existing Notion trackers).
