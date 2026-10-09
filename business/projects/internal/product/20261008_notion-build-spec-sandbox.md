---
title: "Notion Build Spec — Operating System (v2, Phases 1–3)"
date: 2026-10-08
tags: [project, tool, ai]
ai: claude
status: needs-attention
---

# Notion Build Spec: Operating System (v2)

## Summary
The master spec for having **Notion AI** build the Notion half of the AI-native operating architecture: databases, properties, relations, page templates, views and seed pages. Built in three phases, **one phase at a time**. **v2** folds in everything Notion AI reported after building v1 in JC's sandbox (what broke, what needed a judgement call, what can only be done by hand). Use v2 for every future build, starting with MOG.

## Context
- Source design: [[business/projects/internal/product/20261008_ai-native-operating-architecture]] (Sections 3, 4, 10, 12). Decisions: [[business/projects/internal/product/20261008_ai-native-architecture-decision-log]].
- **How to use this file:** paste the **Opening prompt**, the **Global rules**, the **Builder notes**, and **one phase** into Notion AI. Don't paste all phases at once. After each phase, work through that phase's **Manual steps** and **Done when** lists (plus the **Every phase: done when** list) before starting the next.
- **Version history:**
  - v1 (2026-10-08): first spec; sandbox built from it in JC's workspace.
  - v2 (2026-10-08): integrated Notion AI's build feedback: exact relation cardinality and both-side descriptions, rollup calculations, formula types and exact formulas, archive rules per database, default "All" views, hub-page view descriptions, change log, Notion AI Meeting Notes, follow-up tracking, manual-steps lists, restricted-area method, pinned view definitions, extra checks.

---

## Content

### Opening prompt (paste first)

> You're building the Notion workspace for a small firm's AI-native operating system inside a new top-level page called **"Operating System"** (for a sandbox, **"Operating System (Sandbox)"**). Follow the spec below exactly. Build **only the phase I give you**. Use the exact database names, property names, property types, select options, relation limits, rollup calculations and formulas listed. Every property gets the description given, including the other side of every relation. If something in the spec isn't possible in Notion, or can only be done by hand in the Notion app, **don't improvise silently**: build the closest alternative, add the item to the phase's manual-steps list, and report it at the end. When you're done, give me: every database with its link, every view and template, any spec item you changed, and the manual steps still to do.

### Global rules (paste with every phase)

1. **Names are exact.** Use the database and property names as written. **No emoji or icons in database or page names**; icons go in the icon field only. Don't add databases or properties that aren't in the spec. **If a view needs a property, that property is in the spec**; if it isn't, stop and report it.
2. **Select values are lowercase,** exactly as listed.
3. **Every property gets its description** (the text in the Description column).
4. **Every relation is two-way.** For each relation the spec gives: the property name on both sides, **one or many on each side**, and **a description for each side**. Set "limit to one page" only on the side marked *one*.
5. **Every database has these standard properties:**
   - **Summary** (Text): One line describing the current state of this item. Kept current; agents read this instead of opening the page.
   - **Needs Attention** (Checkbox): Checked when a person needs to look at this item.
   - **Created** (Created time): Set automatically. Never edit.
   - **Last Edited** (Last edited time): Set automatically. Never edit.
6. **No orphan pages.** Every content page is a row in a database. The only free-standing pages are: the top-level page, **Home**, **Clients**, **All work**, the **person home template ("My page")**, and the **restricted container page** (Phase 3).
7. **Archive with a status, never by deleting.** Every database has either an archived value (named in its section) or the line "append-only, no archive". Default views hide archived rows.
8. **Titles are clean human titles** with no dates or IDs (dates and IDs live in properties). **Exceptions:**
   - **Project titles start with the Project ID:** `{Project ID} {Project name}` (e.g. `ACM-26100201 Operations Build`), so every relation to a project shows its ID and search finds it by ID.
   - **Meeting Notes titles** created by Notion AI Meeting Notes or Notion Calendar keep the automatic title (event name plus date and time).
9. **Client codes** are 3 capital letters (e.g. `ACM`). **Project IDs** use `{CLIENT}-{YYMMDDNN}` (e.g. `ACM-26100101`): client code, the date the project was opened as YYMMDD, and a two-digit sequence for that day. Assigned once, never changed.
10. **Rollups state their calculation.** Every rollup in this spec says which relation, which property and which calculation (usually "Show original"). Never leave the calculation unset.
11. **Formulas state their result type** (text, number, checkbox, date) and give the exact formula.
12. **Default view:** every database gets a default view named **"All {database name}"** (e.g. "All Projects"), a table that hides archived rows and is sorted by Last Edited newest first, unless the database's section says otherwise.
13. **Hub-page views get a heading and a description.** Every linked view on Home, My page, Clients and All work sits under a heading, followed by one italic line saying what's in the view and what to do with it (wording given in each phase). Turn off the database title on these linked views so it doesn't repeat the heading.
14. **Template changes reach existing rows.** When a template gains a section or view, add it to existing rows too, including example data.
15. **Currency:** every currency field uses **US dollars** unless the firm says otherwise.
16. **Relative dates** are written the way Notion filters express them ("within the next week", "before one month ago", "this calendar month"). Where Notion has no exact match, use the closest option and report it.
17. **Change log from day one.** The System Registry has a Change log table (Date | What | Why | Approved by). Every change, including deprecations, is logged there and on the affected database's registry page.

### Builder notes (for whoever builds it, person or agent)
- **Relations:** write a relation from one side only, one change at a time per row, then re-read the row to check it saved. Saving several relation changes at once can silently drop some.
- **One-page limits:** after limiting a relation to one page, check the other side didn't get the same limit.
- **Rollups and formulas:** after creating one, check it returns a value on a real example row.
- **Views:** after building, check every view against the example data. Linked-view column visibility can't be confirmed through the API; check it in the app.
- **API limits seen in v1:** grouping a view by a formula or rollup, and row limits on linked views ("load 10"), couldn't be set through the API. These are manual steps.

---

### Phase 1: Foundations

**Build:** Companies, People, Projects, Tasks, Knowledge; Home, Clients and My page; the System Registry, registry pages, quick reference and Getting started pages; example data.

#### 1.1 Companies
Clients, partners and vendors. Base client context lives on the page. **Archived value:** Status = archived.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Company name. |
| Client Code | Text | 3 capital letters | Unique 3-letter code used in every project ID. Never changed or reused. |
| Type | Select | client, partner, vendor, internal | What kind of company this is. |
| Status | Select | active, paused, past, archived | Current relationship status. |
| People | Relation → People | see Relations | Contacts who work at this company. |
| Projects | Relation → Projects | see Relations | All projects for this company. |
| Drive Folder | URL | | Link to this company's client folder in Google Drive. |
| AI Rules | Text | | Any restrictions on how AI may use this client's information. Read before every task. |
| Owner | Person | | Team member responsible for the relationship. |
| + standard properties | | | |

**Page template ("Company"), set as default:** headings in this order: **Overview**, **People and roles**, **Scope history**, **Tools they use**, **AI rules**, **Preferences**, **History**. Then a linked view **Projects**: this company's projects; table; sorted by Stage, then Last Edited newest first; hides archived and done.

#### 1.2 People
Client-side and external contacts only. Team members are Notion users, not rows here. **Archived value:** Relationship Stage = archived.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Person's full name. |
| Company | Relation → Companies | see Relations | The company this person works for. Leave empty for early prospects. |
| Email | Email | | Primary email. |
| Phone | Phone | | Primary phone. |
| Title | Text | | Job title. |
| LinkedIn | URL | | LinkedIn profile. |
| Relationship Stage | Select | identified, reached out, in conversation, opportunity, client, past client, dormant, archived | Where this relationship stands. Drives the pipeline board. |
| Last Contacted | Date | | Date of the most recent email or meeting. Will be set by a script; set by hand until then. |
| Next Follow-up | Date | | When to reach out next. |
| Last Talked About | Text | | One line on the most recent substantive conversation. |
| Source | Select | referral, outreach, event, inbound, network | How this relationship started. |
| + standard properties | | | |

The contact-role relations from Projects (Main Contact For, Secondary Contact For, Decision Maker For, Stakeholder For) also appear here.

**Page template ("Person"), set as default:** headings: **About**, **Touchpoints**. Under Touchpoints, an italic note: *"Append-only log, newest at the bottom. One line each: date — what happened — source (human / ai). Only important things: first meetings, intros, pricing or scope talks, contract events, personal details, complaints. Project-specific conversation goes on the project, not here."*

#### 1.3 Projects
Every unit of scoped work: client, internal and admin. Project context lives on the page. **Archived value:** Stage = archived.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | `{Project ID} {Project name}` | Project ID followed by the project name, e.g. "ACM-26100201 Operations Build". The ID part must match the Project ID property exactly. The name part can change; the ID never does. |
| Project ID | Text | `{CLIENT}-{YYMMDDNN}` | Permanent project ID. Assigned once at creation, never changed. Used in Drive folder names and file names. |
| ID Match | Formula (text) | `if(prop("Name").startsWith(prop("Project ID") + " "), "ok", "mismatch")` | Shows "mismatch" when the title no longer starts with the Project ID. Fix the title, never the ID. |
| Area | Select | client, internal, admin | Which part of the business this project belongs to. |
| Company | Relation → Companies | see Relations | The client or company this project is for. Internal and admin projects relate to the firm's own company row. |
| Stage | Select | discovery, proposal, signed, active, ongoing, done, lost, archived | Where the project stands. "ongoing" is for evergreen projects with no end date. |
| Main Contact | Relation → People | see Relations | Main client-side contact for this project. |
| Secondary Contact | Relation → People | see Relations | Backup client-side contact. |
| Decision Maker | Relation → People | see Relations | Who signs off on this project. |
| Stakeholders | Relation → People | see Relations | Other people with a stake in this project. |
| Owner | Person | | Team member who owns delivery. |
| Start Date | Date | | When work started. |
| Target End | Date | | Planned end date. Empty for ongoing projects. |
| Drive Folder | URL | | Link to this project's folder in Google Drive. |
| Tasks | Relation → Tasks | see Relations | Tasks under this project. |
| + standard properties | | | |

**Note:** a template can't fill in the Project ID. Whoever creates a project types the ID into both the title and the Project ID property (later, the promotion skill does this). ID Match catches mistakes.

**Page template ("Project"), set as default.** This page works like a folder. Sections in this **fixed order** (later phases insert into it):
1. A callout: **"Project ID:"** followed by the Project ID, and **"Drive folder:"** followed by the Drive Folder link.
2. Heading **Where things stand**, with sub-headings **Current state**, **Open items**, **Watch items**, and an italic note: *"Rewritten at the end of each working session. Keep it short."*
3. Heading **Scope**.
4. Heading **Decisions** (dated bullets, newest at the bottom).
5. Heading **Tasks**: linked view of Tasks for this project; Status is not done, cancelled or archived; sorted by Due.
6. *(Phase 2)* **Drafts**, then **Meetings**, then **Handoffs**.
7. *(Phase 3)* **Documents**.

#### 1.4 Tasks
**Archived value:** Status = archived.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | What needs doing, as an action. |
| Project | Relation → Projects | see Relations | The project this task belongs to. |
| Owner | Person | team members only | Who is doing it. |
| Due | Date | | When it's due. |
| Status | Select | to do, doing, waiting, done, cancelled, archived | Current state of the task. |
| Priority | Select | high, medium, low | How important it is. |
| + standard properties | | | |

#### 1.5 Knowledge
Company-level living knowledge: SOPs, guides, training, policies, the quick reference and the System Registry. **Archived value:** Status = archived.

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

Besides "All Knowledge", add a view **"By type"** grouped by Type.

#### 1.6 Phase 1 relations

| From (property, one/many) | To (property, one/many) | Description, from side | Description, to side |
|---|---|---|---|
| People.Company (**one**) | Companies.People (**many**) | The company this person works for. | Contacts who work at this company. |
| Projects.Company (**one**) | Companies.Projects (**many**) | The client or company this project is for. | All projects for this company. |
| Projects.Main Contact (**one**) | People.Main Contact For (**many**) | Main client-side contact for this project. | Projects where this person is the main contact. |
| Projects.Secondary Contact (**one**) | People.Secondary Contact For (**many**) | Backup client-side contact. | Projects where this person is the backup contact. |
| Projects.Decision Maker (**one**) | People.Decision Maker For (**many**) | Who signs off on this project. | Projects this person signs off on. |
| Projects.Stakeholders (**many**) | People.Stakeholder For (**many**) | Other people with a stake in this project. | Projects this person has a stake in. |
| Tasks.Project (**one**) | Projects.Tasks (**many**) | The project this task belongs to. | Tasks under this project. |

#### 1.7 System Registry and seed pages (Knowledge rows)

**"System Registry"** (Type = system, Audience = admins). Body, five tables (each later phase appends to them):
1. **Database index:** Database | Purpose | Owner | Core (yes/no) | Locked (yes/no) | Link.
2. **Relationships:** From | To | Property (from side) | Property (to side) | One/many | Why. Fill from the relations tables in this spec.
3. **Standard views:** View | Database | Filter | Sort | Group.
4. **Change protocol:** the eight rules below.
5. **Change log:** Date | What | Why | Approved by. First row: today's date, "Initial build, Phase 1", "Build from spec v2", the person who ran it.

**One "Registry: {Database}" page per database** (Type = system), each with these sections in order: **Purpose**, **Owner and approvers**, **Who writes / who reads**, **AI access**, **Sensitivity**, **Key properties**, **Relations**, **Skills and views that depend on it**, **Core** (yes), **Lock status** (unlocked until reviewed), **Database link**.

**"How to use this system"** (Type = quick-reference, Audience = everyone, Status = draft). Draft it from the outline below.

**"Getting started"** (Type = training, Audience = everyone, Status = draft). Short: what the system is for, the Home page, your own page, where to ask questions.

**Change protocol text:**
1. Add a property before adding a database. A new database only when lifecycle, permissions or cardinality differ; a filtered subset is a view.
2. Don't rename or delete properties or select options. Add, deprecate and migrate instead; log deprecations in the change log.
3. Every relation is two-way, named and described on both sides, with one/many set and its reason recorded.
4. Every property gets a description. Select values are lowercase.
5. Try changes in a scratch copy first.
6. Order of work: registry → schema → skills → backup manifest → views and templates → quick reference and training.
7. Anything involving money, legal, HR or client confidentiality starts in a restricted area.
8. Log every change: date, what, why, who approved.

**Quick reference outline ("How to use this system"):**
1. **Where things live:** Notion = drafts, context, people, projects, tasks, meetings, knowledge. Google Drive = finals and files clients receive. Gamma = presentations. Billing tool = money.
2. **How to find anything:** start at Home; Clients → company → project; every project page has its tasks, drafts, meetings and handoffs.
3. **Tip: find by ID.** Every project's title starts with its ID, so typing a project ID (`ACM-26100101`) or a client code (`ACM-`) into search finds it straight away. The same works in any view's filter. Anywhere a project is linked, you'll see its ID.
4. **Naming in one line each:** titles are clean, except project titles, which start with the project ID; project IDs are `{CLIENT}-{YYMMDDNN}`; internal Drive files start `YYYYMMDD_{ID}_`; client-facing files get clean titles.
5. **Keep Summary current** and tick Needs Attention when someone needs to look.
6. **What AI will and won't do:** drafts and prepares; never sends to clients, never touches money, never publishes, never changes the system without approval.
7. **Start and end a session:** start by reading the project's "Where things stand"; end by writing a Handoff and updating "Where things stand" (Phase 2).
8. **After a meeting** (Phase 2): every commitment becomes a Task; tick Requires Follow-up if you owe someone something, and Followed Up when it's done.
9. **Need a change?** Ask the system owner; changes follow the change protocol in the System Registry.

#### 1.8 Hub pages and views

**Home** (free-standing). Linked views in this order, each with its heading and italic description:

| Heading | View | Description line |
|---|---|---|
| Projects needing attention | Projects where Needs Attention is checked | *Projects someone has flagged. Open each one, deal with it, then untick Needs Attention.* |
| Tasks needing attention | Tasks where Needs Attention is checked, or Due is on or before today and Status is not done, cancelled or archived | *Flagged or overdue tasks across everyone. Unlike "This week", this shows only what's late or flagged.* |
| This week | Tasks due within the next week, Status not done, cancelled or archived, sorted by Due | *Everything due in the next seven days, for everyone. Your own list is on My page.* |
| Follow-ups due | People where Next Follow-up is on or before today | *Contacts you meant to get back to. Reach out, then set a new Next Follow-up date.* |
| Pipeline | Board of People grouped by Relationship Stage, hiding client, past client, dormant and archived | *Prospects by stage. Drag a card when a relationship moves forward.* |
| Active projects | Projects where Stage is discovery, proposal, signed, active or ongoing, sorted by Last Edited newest first | *All live work, most recently touched first. Open a project to see its tasks, drafts and meetings.* |

Then links to **Clients**, **All work** (Phase 2), **Knowledge**, **How to use this system**.

**Clients** (free-standing):

| Heading | View | Description line |
|---|---|---|
| Projects by client | Projects table, Area = client, grouped by Company, sorted by Stage; hides done and archived | *Every client and its live projects. Expand a client to see its work; open a project to go deeper.* |
| Active companies | Companies table, Status = active | *Who we currently work with. Open a company for its background, people and AI rules.* |

**My page** (person home template; views filtered to **Me**):

| Heading | View | Description line |
|---|---|---|
| My tasks | Tasks where Owner is Me, Status not done, cancelled or archived, sorted by Due | *Everything assigned to you that's still open, soonest first.* |
| My projects | Projects where Owner is Me, Stage not done or archived | *Projects you own. Keep their "Where things stand" current.* |
| My attention items | Tasks where Owner is Me and Needs Attention is checked | *Your flagged tasks. Deal with them, then untick Needs Attention.* |
| Private notes | (heading only) | *Your own scratch space.* |

#### 1.9 Example data (all marked EXAMPLE)
- **Companies:** "EXAMPLE Blue Tusk" (`BTK`, internal, active); "EXAMPLE Acme Advisory" (`ACM`, client, active); "EXAMPLE Oakridge Logistics" (`OAK`, client, active).
- **People:** two per client company (one with Relationship Stage = client), plus two prospects with no company (reached out; in conversation, with Next Follow-up in the past).
- **Projects** (title includes the ID):
  - "ACM-26100101 EXAMPLE Discovery and Roadmap" — client, Acme, done.
  - "ACM-26100201 EXAMPLE Operations Build" — client, Acme, active; Main Contact and Decision Maker set.
  - "OAK-26100501 EXAMPLE Logistics Proposal" — client, Oakridge, proposal.
  - "BTK-26100801 EXAMPLE Outreach Q4" — internal, Blue Tusk, ongoing.
  - "BTK-26100802 EXAMPLE Finance and Admin" — admin, Blue Tusk, ongoing.
- **Tasks:** 6–8 across the projects; mixed statuses; one overdue; one with Needs Attention checked; at least two owned by the builder so My page shows them.
- **Summary** filled on every example row; **Where things stand** filled on the active project.

#### Phase 1 manual steps (in the Notion app)
- [ ] Turn off the database title on every linked view on Home, Clients and My page.
- [ ] Hide noisy columns in linked views (e.g. Created, Last Edited, ID Match) and check which columns show.
- [ ] Set each page template as the database default (Company, Person, Project).

#### Phase 1 done when
- [ ] Five databases exist with exactly the listed properties, types, options and descriptions.
- [ ] Every project title starts with its Project ID; ID Match shows "ok" on every example project.
- [ ] A task's Project relation shows the project's ID; searching `ACM-26100201` finds that project.
- [ ] The System Registry has all five tables, one registry page per database in the standard format, and a first change-log row.
- [ ] "How to use this system" and "Getting started" exist as drafts.

---

### Phase 2: Working layer

**Build:** AI Drafts, Meeting Notes, Handoffs; the Project template's Drafts, Meetings and Handoffs sections (on the template **and** existing projects); All work; additions to Home and My page; registry updates; example data.

#### 2.1 AI Drafts
All drafts of all documents. Notion is always drafts; finals live in Google Drive or Gamma. **Archived value:** Status = archived.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Clean human title, the same title the final will have. |
| Project | Relation → Projects | see Relations | The project this draft belongs to. |
| Project ID | Rollup | relation Project → property Project ID → **Show original** | Project ID, pulled from the project. |
| Client Code | Formula (text) | `prop("Project").first().prop("Project ID").substring(0, 3)` | Client code, the first three characters of the project's ID. Used to group drafts by client. |
| Drive Folder | Rollup | relation Project → property Drive Folder → **Show original** | Where the final will go. |
| Type | Select | document, email, proposal, sop, report, deck-outline, sheet, post, other | What kind of draft this is. |
| Audience | Select | internal, client | Who will receive the final. Sets how the final file is named. |
| Status | Select | draft, in progress, sent, published, archived | draft = in Notion; in progress = Google file exists but isn't final; sent / published = delivered. |
| Destination | Select | google-drive, gamma, client-workspace, email, notion | Where the final will live. |
| Final Link | URL | | Link to the final file once it exists. |
| AI | Select | human, claude, notion-ai | Who wrote the draft. |
| Tags | Multi-select | (start empty) | Free tags. |
| Created By | Created by | | Set automatically. Used by "My drafts". |
| + standard properties | | | |

Besides "All AI Drafts", add **"Stale drafts"**: Status = draft and Last Edited before one month ago.

#### 2.2 Meeting Notes
Meeting records: transcript, summary, decisions and follow-ups. **Append-only record, no archive.**

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | automatic title allowed (rule 8) | Meeting name. |
| Date | Date | | When the meeting happened. |
| Project | Relation → Projects | see Relations | The project this meeting was about. |
| Attendees | Relation → People | see Relations | External attendees. |
| Team Attendees | Person | | Team members who attended. |
| Meeting Type | Select | client, prospect, internal, partner | What kind of meeting. |
| Requires Follow-up | Checkbox | | Checked when someone owes a follow-up from this meeting. |
| Followed Up | Checkbox | | Checked once the follow-up has been sent or done. |
| Source | URL | hidden in views | Only for meetings recorded outside Notion: link to that transcript or recording. |
| AI | Select | human, claude, notion-ai | Who wrote the notes. |
| + standard properties | | | |

**Page template ("Meeting"), set as default:** a single **AI Meeting Notes** block (it produces the transcript, summary and action items). Turning commitments into Tasks is a person's job (see the quick reference) or a future skill; the template doesn't carry it.

#### 2.3 Handoffs
One row per working session. **Append-only timeline, no archive status. Rows are never edited after creation.**

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Short label, e.g. "Build plan drafted". |
| Projects | Relation → Projects | see Relations | Projects this session touched. |
| Written By | Select | human, claude, notion-ai | Who wrote this handoff. Needed because agent edits show under the connected person's name. |
| Author | Person | | The person who ran the session. |
| Created By | Created by | | Set automatically. |
| + standard properties | | | |

**Page template ("Handoff"), set as default:** headings **Done**, **Open**, **Next**.

#### 2.4 Phase 2 relations

| From (property, one/many) | To (property, one/many) | Description, from side | Description, to side |
|---|---|---|---|
| AI Drafts.Project (**one**) | Projects.Drafts (**many**) | The project this draft belongs to. | Drafts for this project. |
| Meeting Notes.Project (**one**) | Projects.Meeting Notes (**many**) | The project this meeting was about. | Meetings about this project. |
| Meeting Notes.Attendees (**many**) | People.Meetings (**many**) | External attendees. | Meetings this person attended. |
| Handoffs.Projects (**many**) | Projects.Handoffs (**many**) | Projects this session touched. | Working-session handoffs on this project. |

#### 2.5 Project template additions (template and every existing project)
After the Tasks section, in order, each sorted by Last Edited newest first unless stated:
- **Drafts:** AI Drafts for this project, not archived.
- **Meetings:** Meeting Notes for this project, sorted by Date newest first.
- **Handoffs:** Handoffs for this project, newest first, **last 10** (row limit is a manual step).

#### 2.6 All work (free-standing page, linked from Home)

| Heading | View | Description line |
|---|---|---|
| All drafts by client | AI Drafts table, archived hidden, **grouped by Client Code**, sorted by Project ID then Last Edited | *Every draft, grouped by client. Expand a client to see its drafts across all projects.* |
| Board by client | AI Drafts board grouped by Client Code, **sub-grouped by Project ID only if the app allows it** | *The same drafts as cards, for a quick scan by client and project.* |

**Fallback (grouping by a formula or rollup can't be set through the API):** first try grouping by Client Code by hand in the Notion app. If the app doesn't allow it, group by **Project** instead; because project titles start with their ID, the groups still read in client order. Record which method was used in Standard views.

#### 2.7 Home and My page additions
**Home** (add after "Tasks needing attention"):

| Heading | View | Description line |
|---|---|---|
| Drafts needing attention | AI Drafts where Needs Attention is checked | *Drafts someone has flagged for review.* |
| Follow-ups owed | Meeting Notes where Requires Follow-up is checked and Followed Up is not | *Meetings where we still owe someone something. Send it, then tick Followed Up.* |
| Recent drafts | AI Drafts edited within the past week, archived hidden | *Drafts touched in the last seven days, across everyone.* |

**My page:**

| Heading | View | Description line |
|---|---|---|
| My drafts | AI Drafts where Created By is Me, archived hidden | *Drafts you started that aren't archived.* |
| My meetings | Meeting Notes where Team Attendees contains Me, Date within the past two weeks (or past month if two weeks isn't available) | *Your recent meetings.* |
| My follow-ups owed | Meeting Notes where Team Attendees contains Me, Requires Follow-up checked, Followed Up not checked | *Follow-ups you owe from your meetings.* |

#### 2.8 Registry and quick reference
- Add "Registry: AI Drafts", "Registry: Meeting Notes", "Registry: Handoffs" (standard format).
- Append to Database index, Relationships and Standard views; add a change-log row.
- Make points 7 and 8 of "How to use this system" live now that Handoffs and Meeting Notes exist.

#### 2.9 Example data (marked EXAMPLE)
- 4–6 drafts across the example projects: mixed Type, Audience and Status; one published with a placeholder Final Link. *(A stale draft can't be faked, because Last Edited can't be backdated; the Stale drafts view fills after a month.)*
- 2–3 meeting notes on "ACM-26100201 EXAMPLE Operations Build" with attendees; one with Requires Follow-up checked and Followed Up unchecked; matching Tasks for the commitments.
- 2 handoffs on that project, one Written By human and one claude.

#### Phase 2 manual steps (in the Notion app)
- [ ] **Default meetings database:** Settings → Notion AI → set the default meetings database to Meeting Notes.
- [ ] **Handoffs view on the Project template:** set Load → 10.
- [ ] **All work:** group by Client Code by hand if the app allows it; otherwise apply the fallback.
- [ ] Hide Source and other noisy columns in linked views; turn off database titles on new hub-page views.

#### Phase 2 done when
- [ ] Three databases exist exactly as listed; the Project ID and Drive Folder rollups and the Client Code formula return values on an example draft.
- [ ] Every existing project, not just the template, shows Drafts, Meetings and Handoffs for that project only.
- [ ] All work groups drafts by client (or the recorded fallback).
- [ ] Follow-ups owed and My follow-ups owed each show the example meeting.
- [ ] Registry, change log and quick reference are updated.

---

### Phase 3: Registers (build only when asked)

**Build:** Documents (in the main area); Contracts and Invoices (in the restricted area); their views; registry updates; example data.

#### 3.0 Restricted area (do this first)
1. **Check for teamspaces.** If the plan supports teamspace permissions, create a restricted teamspace for Contracts and Invoices.
2. **If there are no teamspaces,** create a **private top-level page outside the main "Operating System" page**, named **"Operating System (Restricted)"**. Don't nest it inside the main page: a nested page inherits the main page's sharing.
3. Share it only with admins.
4. **Test it with a non-admin account,** not just by assumption.

**Known limits (write these into the registry pages):**
- Notion can't restrict a single block on a page. Restricted views on Home rely on the databases' own access; non-admins see an empty or locked block.
- Contracts and Invoices relation columns appear on Companies and Projects for everyone. Non-admins see the column but can't open the rows. **Hide these columns in shared views.**
- "Written only by scripts" (Invoices amounts and status) can't be enforced in Notion. It's a policy, not a lock.

#### 3.1 Documents
Register of files clients send. Originals live in Drive. **Archived value:** Status = archived.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | original file name allowed | Original file name. |
| Project | Relation → Projects | see Relations | Project the file belongs to. |
| Company | Relation → Companies | see Relations | Company that sent it. |
| Sender | Relation → People | see Relations | Who sent it. |
| Received | Date | | When it arrived. |
| Drive Link | URL | | Link to the original in Drive. |
| Key Facts | Text | | The important facts from the file, so it doesn't need re-reading. |
| Status | Select | new, processed, needs action, archived | Processing state. |
| AI Access | Select | allowed, restricted | Whether AI may read the file. Restricted files get a human-written summary. |
| + standard properties | | | |

**Page template ("Document"), set as default:** AI Access preset to **allowed** *(open decision: restricted-by-default is safer but means every file needs a human summary)*. Add the **Documents** section to the Project template and every existing project (after Handoffs): Documents for this project, archived hidden, sorted by Received newest first.

#### 3.2 Contracts (restricted area)
**Archived values:** Status = expired or terminated.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Contract name. |
| Type | Select | msa, sow, nda, amendment, other | Contract type. |
| Company | Relation → Companies | see Relations | Counterparty. An MSA relates to the company. |
| Project | Relation → Projects | see Relations | A SOW relates to its project. |
| Parent Contract | Relation → Contracts | see Relations | A SOW's MSA. |
| Status | Select | draft, sent, signed, active, expired, terminated | Contract state. |
| Signed Date | Date | | When it was signed. |
| Term End | Date | | When it ends. |
| Renewal Date | Date | | When it renews or needs a decision. |
| Value | Number | US dollars | Contract value. |
| Drive Link | URL | | Link to the signed PDF. |
| + standard properties | | | |

**Views:**
- **All Contracts** (default): hides expired and terminated.
- **Unsigned:** Status is draft or sent.
- **Active:** Status is signed or active.
- **Renewing in 90 days:** Renewal Date within the next 90 days; excludes expired and terminated.
- **By company:** grouped by Company.

#### 3.3 Invoices (restricted area)
The billing tool is the source of truth; this is the register. **Amounts and payment status are written only by scripts (policy, not enforceable).** **Archived value:** Status = void.

| Property | Type | Options / notes | Description |
|---|---|---|---|
| Name | Title | | Invoice number. |
| External ID | Text | | The invoice's ID in the billing tool. |
| Billing System | Select | stripe, quickbooks, wise, other | Which tool issued it. |
| Project | Relation → Projects | see Relations | Project billed. |
| Company | Relation → Companies | see Relations | Company billed. |
| Amount | Number | US dollars | Invoice amount. Set by script. |
| Issued | Date | | Issue date. |
| Due | Date | | Due date. |
| Status | Select | draft, sent, paid, overdue, void | Payment status. Set by script. |
| Paid Date | Date | | When it was paid. Set by script. |
| Link | URL | | Link to the invoice in the billing tool. |
| + standard properties | | | |

**Views:**
- **All Invoices** (default): hides void.
- **Unpaid:** Status is sent or overdue (not draft).
- **Overdue:** Status is overdue (the script sets it).
- **Paid this month:** Paid Date in this calendar month.

#### 3.4 Phase 3 relations

| From (property, one/many) | To (property, one/many) | Description, from side | Description, to side |
|---|---|---|---|
| Documents.Project (**one**) | Projects.Documents (**many**) | Project the file belongs to. | Files the client sent for this project. |
| Documents.Company (**one**) | Companies.Documents (**many**) | Company that sent it. | Files this company has sent. |
| Documents.Sender (**one**) | People.Documents Sent (**many**) | Who sent it. | Files this person has sent. |
| Contracts.Company (**one**) | Companies.Contracts (**many**) | Counterparty. | Contracts with this company. |
| Contracts.Project (**one**) | Projects.Contracts (**many**) | The project a SOW covers. | Contracts for this project. |
| Contracts.Parent Contract (**one**) | Contracts.Child Contracts (**many**) | A SOW's MSA. | SOWs and amendments under this contract. |
| Invoices.Project (**one**) | Projects.Invoices (**many**) | Project billed. | Invoices for this project. |
| Invoices.Company (**one**) | Companies.Invoices (**many**) | Company billed. | Invoices to this company. |

#### 3.5 Admin section on Home
Add a heading **Admin (restricted)** at the bottom of Home with an italic line: *"Visible only to admins. Others will see empty or locked blocks."*

| Heading | View | Description line |
|---|---|---|
| Unpaid invoices | Invoices: Unpaid | *Sent and overdue invoices. Chase overdue ones.* |
| Contracts renewing | Contracts: Renewing in 90 days | *Contracts that renew or need a decision in the next 90 days.* |

#### 3.6 Registry
- Registry pages for Documents, Contracts and Invoices live in Knowledge and contain **setup information only** (no contract or invoice data). Include the known limits from 3.0.
- Append to all registry tables; add a change-log row.

#### 3.7 Example data (marked EXAMPLE)
- 2 documents on "ACM-26100201 EXAMPLE Operations Build" (one processed, one new).
- An MSA with Acme, and a SOW under it for the Operations Build project (Parent Contract set).
- 3 invoices across statuses (paid this month, sent, overdue), so every invoice view shows a row.

#### Phase 3 manual steps (in the Notion app)
- [ ] Set up restricted-area sharing (admins only) and test with a non-admin account.
- [ ] Hide the Contracts and Invoices columns on Companies and Projects in shared views.
- [ ] Turn off database titles on the admin views on Home.

#### Phase 3 done when
- [ ] Documents exists, with the Documents section on the template and every existing project.
- [ ] Contracts and Invoices live in the restricted area; a non-admin test account can't open them.
- [ ] Every Contracts and Invoices view shows at least one example row.
- [ ] Registry pages, tables and change log are updated.

---

### Every phase: done when
- [ ] Database names match exactly, with no emoji.
- [ ] Every property has a description, including the other side of every relation.
- [ ] One or many is set and checked on both sides of every relation.
- [ ] Every rollup and formula returns a value on an example row.
- [ ] Every database has an "All {name}" default view that hides archived rows (or is marked append-only).
- [ ] Every hub-page view has a heading and a description line.
- [ ] Template changes are applied to existing rows.
- [ ] Every view shows at least one example row, or the reason it can't is noted.
- [ ] Registry updated: index, relationships, standard views, change log.
- [ ] The phase's manual steps are done and ticked.
- [ ] (Phase 3) Restricted area tested with a non-admin account.

### Out of scope for Notion AI (don't build)
- **Google Drive folders,** INDEX and CONVENTIONS (built separately; Notion stores links only).
- **Scripts:** backups, Last Contacted updater, payment webhooks, reconciliation, drift checks.
- **The skills repo** and skill deployment.
- **Database locks:** applied by hand after each phase is reviewed.
- **Migration of real data:** a separate spec after the sandbox is approved.

### Open decisions in this spec
- **Documents AI Access default:** allowed (current) vs restricted (safer, more human work).
- **Meeting Notes titles:** keep the automatic title (current exception in rule 8) vs a "trim the title" step.
- **Currency:** USD default; MOG may need a second currency because of Wise.

## Next steps
- [ ] Compare the v1 sandbox against v2 and fix any gaps (most were fixed during the build).
- [ ] Record the sandbox's database links in its System Registry.
- [ ] Decide the open decisions above.
- [ ] Lock core databases by hand after review.
- [ ] Write the migration spec for JC's active work (contacts, projects, existing Notion trackers).
- [ ] Use v2 for the MOG build once Martina's questions are answered.
