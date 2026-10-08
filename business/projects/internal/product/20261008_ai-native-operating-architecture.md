---
title: "AI-Native Operating Architecture — Reference Design (v1)"
date: 2026-10-08
tags: [project, strategy, ai, tool, offer]
ai: claude
status: needs-attention
---

# AI-Native Operating Architecture: Reference Design (v1)

## Summary
This is a reusable architecture for running a small firm with AI agents doing much of the drafting, filing, tracking and catch-up work, at a token cost the firm can afford. It was designed with JC on 2026-10-07 and 2026-10-08 for **Madrid Operations Group (MOG)**. It is written to apply to **any company Blue Tusk sets this up for, eventually including Blue Tusk itself.**

**The core idea in one line:** **Notion is the working back end** (drafts, context, records and dashboards), **Google Drive holds finals and files** (anything people receive, sign or share), and **AI agents follow fixed rules about which they read, which they write, and how cheaply.**

The main design choices:
- **Notion is always drafts; Google Docs are always finals.** Editing in Notion costs roughly 15 to 200 times less than editing an existing Google Doc. *(Measured.)*
- **One ID per entity, used everywhere:** a 3-letter client code plus a project ID, `{CLIENT}-{YYMMDDNN}`, in Notion, Drive and the vault.
- **Ten Notion databases:** Companies, People, Projects, Tasks, Meeting Notes, AI Drafts, Documents, Contracts, Invoices and Knowledge. Built in stages.
- **Agents work across a client's projects but never across clients.**
- **Every database row has a one-line summary,** so agents catch up by querying instead of reading pages.
- **A scripted (not AI) backup** exports everything to markdown with frontmatter, keeping relations rebuildable.
- **Governance:** a System Registry, a change protocol, locks on core databases, and permission-based schema changes.

**Status:** the design is v1. Notion editing costs have been tested; several other items are designed but untested (see Section 15). Firm-specific details are marked **[per firm]**; everything else is the generalizable pattern.

## Context
**Where this came from:**
- The MOG engagement: [[business/projects/client-projects/26092901_madrid-operations-group-AI-first-retainer/20261007_MOG_AI_Native_Stack_Architecture]] and the current-state workflow map.
- Hands-on connector tests: [[business/projects/internal/product/20261007_google-drive-taxonomy-test-results]].
- JC's own Drive restructure: [[business/projects/internal/google-drive-restructure/20261007_blue-tusk-drive-map-and-proposed-taxonomy]].
- Blue Tusk's offering stack and free-tier taxonomy principles: [[business/projects/internal/product/20260814_information-taxonomy-offering-stack]] and [[business/projects/internal/product/20260818_File_Taxonomy_Free_Tier_Principles]].

**Decision history:** every decision here, with its date and rationale, is in [[business/projects/internal/product/20261008_ai-native-architecture-decision-log]].

---

## Content

### 1. Design principles
1. **Token cost is a design constraint, not an afterthought.** Every workflow is designed around the cheapest read and write path that does the job. *(Measured costs in Section 13.)*
2. **Make information legible before automating it.** Structure, IDs and conventions come first; automations come after. This is the taxonomy layer of Blue Tusk's offering.
3. **Draft and confirm.** AI and assistants prepare; named humans approve anything that goes to a client, involves money, is published, or changes the system.
4. **One identifier per entity, everywhere.** It's the same in Notion, Drive, the vault, email labels and invoices (free-tier principle #2).
5. **Client isolation by structure.** Agents may use all of a client's history but never mix clients.
6. **Agents navigate by ID, never by searching the whole workspace.** Drive search returns every client's files (tested).
7. **AI-agnostic and recoverable.** Everything exports to plain markdown with frontmatter and rebuildable relations. No vendor holds the only copy.
8. **One place to look.** Notion is the single dashboard for people; agents query it instead of hunting.
9. **Deterministic jobs get scripts, not AI.** Backups, payment status and contact recency are handled by small scripts. AI is for judgment and drafting.
10. **Governed change.** The system can grow, but only through a registry, a change protocol and approvals.

### 2. System map: what each tool is for

| System | Role | Holds | Agents may |
|---|---|---|---|
| **Notion** | Working back end and dashboard | Drafts, living client and project context, CRM, projects and tasks, meeting notes, registers (documents, contracts, invoices), knowledge, system registry | Read and write (cheap); schema changes only with approval (Section 12) |
| **Google Drive** | Finals and files | Final documents, client-sent files, signed contracts (PDF), templates, restricted HR records | Create finals in the right folder; read files; rename; **cannot move files** (tested); edit finals only with cheap methods |
| **Gamma** | Presentations | Decks (drafted and finalized there) | Create and edit decks; the Notion draft holds the outline and links to Gamma |
| **Billing tool** [per firm] | Source of truth for money | Invoices and payments: **Stripe** (Blue Tusk); **QuickBooks + Wise** (MOG) | Never mark payments; webhooks and reconciliation scripts update Notion |
| **Email and calendar** | Inputs | Correspondence, meetings | Read for touchpoints and intake (scheduled), draft replies; never send without approval |
| **Meeting notes tool** [per firm] | Transcripts | Fireflies or Notion meeting notes | Read transcripts; write close-outs to Notion Meeting Notes |
| **Backup repo** (private git) + Drive snapshot | Disaster recovery | Markdown export of all core Notion databases | **No agent access** in normal work |
| **Client-owned systems** | Delivery destinations | Client's SharePoint, Notion, HubSpot, Slack, etc. | Deliver finals there when the client works there; the Notion draft records the destination |

### 3. Identity and naming

**3.1 Client codes**
- **Format:** 3 capital letters, fixed length, unique, **never reused**.
- Registered in the Companies database and in Drive INDEX.
- Internal work gets its own code (e.g. `BTK` for Blue Tusk).
- **The Company record, with its code, is created only when a prospect is promoted to a Project** (Section 5.1).

**3.2 Project IDs**
- **Format:** `{CLIENT}-{YYMMDDNN}`, e.g. `MOG-26092901`.
- **Assigned once, never changed.** The descriptive slug can change; the ID can't.
- **The client code goes first** because the ID then reads in the same order as the folder path (client, then project). The ID alone tells an agent which client folder to open, and `MOG-` finds all of a client's work.
- Internal and admin projects use the firm's own code (e.g. `BTK-26100801`).

**3.3 Drive naming**
- Client folder: `{CLIENT}_{client-slug}`, e.g. `MOG_madrid-operations-group/`
- Project folder: `{CLIENT}-{YYMMDDNN}_{project-slug}`, e.g. `MOG-26092901_ai-first-retainer/`
- **Files are named by audience:**
  - **Internal files** use `YYYYMMDD_{CLIENT}-{YYMMDDNN}_description`, e.g. `20261008_MOG-26092901_SOP-Meeting-Close-Out`.
  - **Client-facing finals** use a **clean title**: no date, ID, code or "draft", e.g. `AI-First Rebuild - Build Plan`. Avoid colons. Add `v2` or a date at the end only when re-sent.
  - **Why:** a shared Google Doc shows its file name in the header, the tab, Google's share email and the download. Renaming after download only fixes the download. A rename in Drive keeps the link and ID (tested), but naming correctly from the start is the rule.
- **The ID and date for client-facing files live in the folder name and in Notion properties, not in the file name.**

**3.4 Notion naming**
- **Draft titles are clean, human titles.** The date and project come from properties.
- **Notion and Drive link by URL or file ID, never by name,** so renames never break links.

### 4. Notion data model

**4.1 The databases**

| # | Database | Purpose | Key properties (beyond Name, Created, Last Edited) | Sensitivity |
|---|---|---|---|---|
| 1 | **Companies** | Clients, partners and vendors. **Base client context lives on the page.** | Client code, type, status, AI rules, Drive client folder (URL), Summary, owner | Normal |
| 2 | **People** | Client-side and external contacts only (team members are Notion users) | Company, email, title, Relationship Stage, Last Contacted (script), Next Follow-up, "last talked about", Summary | Personal data |
| 3 | **Projects** | Every unit of scoped work: client, internal, admin. **Project context lives on the page.** | Project ID, Area, Company, Stage, contact roles (relations to People), team owner (Person), Drive folder (URL), Summary, Needs Attention | Normal |
| 4 | **Tasks** | Work items under projects | Project, owner (Notion Person, team only), due date, status, Summary, Needs Attention | Normal |
| 5 | **Meeting Notes** | Meeting close-outs, notes and decisions | Project (two-way relation), attendees (People), date, Summary, source (transcript link) | Normal |
| 6 | **AI Drafts** | **All drafts of all documents.** Notion is always drafts. | Project, Type, Status (draft / ready / published), Audience (internal / client), Destination, Final Link, Drive Folder (rollup from Project), Summary, Needs Attention, AI (claude / human), Tags | Normal |
| 7 | **Documents** | Register of files clients send (originals live in Drive) | Project, Company, sender (People), received date, Drive link, Summary, key facts, status (new / processed / needs action), AI access (allowed / restricted), Needs Attention | Can be sensitive |
| 8 | **Contracts** | Register of MSAs, SOWs, NDAs and amendments (signed PDFs live in Drive) | Type, Company, Project, status, signed date, term end, renewal date, value, parent contract (SOW → MSA), Drive link | **Restricted** |
| 9 | **Invoices** | Register of invoices (billing tool is the source of truth) | Invoice number / external ID, Billing System, Project, Company, amount, issued date, due date, status, paid date, link | **Restricted** |
| 10 | **Knowledge** | Company-level living knowledge: SOPs, how-tos, writing guides, template instructions, HR policies, and the **System Registry** | Type (sop / guide / template-instructions / policy / system), department, audience, owner, Summary, last reviewed, status, Drive template link | Policies normal; system entries admin |

**4.2 Property conventions (apply to every database)**
- **Summary** (one line, always current). Queries return properties, not page bodies, so agents can catch up by scanning rows. **Skills must refresh Summary whenever content changes materially.** A stale summary is a silent error.
- **Needs Attention** (checkbox). Combined with Status, it drives the "open items" view.
- **Created and Last Edited** are automatic system properties. Skills never set them. *(Tested: they update themselves. Created time can't be backdated.)*
- **Frontmatter parity.** Properties mirror vault frontmatter one-to-one (title = Name, date = Created, tags = Tags, ai = AI, status = Status + Needs Attention), so exports become standard markdown notes.
- **Every property has a description.** Agents receive descriptions free with every schema read, so the schema documents itself.
- **Select values are lowercase,** with one consistent naming style.
- **Archive with a status, never by deleting.** Views hide archived rows.

**4.3 Relationships**

| From | To | Property (from side) | Property (to side) | Why |
|---|---|---|---|---|
| People | Companies | Company | People | Contacts belong to one company |
| Projects | Companies | Company | Projects | Every client project belongs to a client |
| Projects | People | Main Contact, Secondary Contact, Decision Maker, Stakeholders | (roles on Projects) | **Roles live on the project**, because the same person can hold different roles on different engagements |
| Tasks | Projects | Project | Tasks | Tasks sit under projects; owner is a Notion user |
| Meeting Notes | Projects | Project | Meeting Notes | Project page lists its notes (two-way) |
| Meeting Notes | People | Attendees | Meetings | Who was there |
| AI Drafts | Projects | Project | Drafts | Replaces a typed Project ID. ID and Drive folder come by rollup. |
| Documents | Projects, Companies, People | Project, Company, Sender | Documents | Register of client-sent files |
| Contracts | Companies, Projects | Company, Project | Contracts | MSA → company; SOW → project |
| Contracts | Contracts | Parent Contract | Child Contracts | SOW → its MSA |
| Invoices | Projects, Companies | Project, Company | Invoices | Billing per engagement |
| Knowledge | (any) | Related | — | Optional links |

**All relations are two-way and named on both sides.**

**4.4 Hierarchy and Area**
- **Hierarchy:** `Area → Project → Task`.
- **Area is a single-select on Projects:** client / internal / admin (admin covers things like finance). It is a property, not a database. Promote it to a database only if an area ever needs its own page.
  - Named "Area" rather than "Scope" to avoid a clash with *scope of work*.
- **No sub-projects.** A project has tasks, which is enough (JC).
- **Company is a relation from Project, not a level in the hierarchy.**

**4.5 Pipeline and CRM**
- **The CRM is the People + Companies base.** The pipeline is views.
- **Early-stage prospects live on People.**
  - **Relationship Stage:** identified → reached out → in conversation → opportunity → client → past client → dormant.
  - The pipeline board is People grouped by stage. "Needs follow-up" is People where Next Follow-up ≤ today.
  - No company or project is needed yet, which avoids flooding Projects with speculative rows.
- **A Project is created when there is scoped work or a document to write** (a free roadmap, a discovery, a proposal). Promotion is in Section 5.1.
- **After promotion, the Project's Stage tracks the deal:** discovery → proposal → signed → active → done / lost.
- **Outreach work itself** (tasks, cold-email drafts) lives in a time-boxed internal project, e.g. "BTK Outreach Q4", following the "everything is a project" principle. The people stay in People.

**4.6 Context: where AI gets its background**
- **Base client context** goes on the **Company page**: people, scope history, tools, AI rules, preferences, history.
- **Project context** goes on the **Project page**: scope, current state, decisions, open items.
- **At the start of any task, an agent reads the Company page and the relevant Project page.** It may read the client's other Projects. It never reads other clients' pages.
- **Why Notion and not Drive:** context changes constantly, which puts it on the cheap-edit side. It's internal and candid. It gets summary and attention queries for free, and the people already work in Notion.
- **Drive holds only a link to the Company page** (in the client folder and in INDEX), never a copy.
- **If a brief becomes client-visible,** publish a copy to Drive following the draft → final rule.
- This **replaces the per-client `_ai/` folder idea** from 2026-10-07 for context and handoffs.

### 5. Core lifecycles

**5.1 Prospect → Project (the promotion skill)**
1. Trigger: scoped work or a document to write.
2. A skill does all of the following **in one run**, because Drive files can't be moved later by agents:
   - Create the **Company** if it's new, and assign its 3-letter code.
   - Create the **Project** and assign its **Project ID**.
   - Create the **Drive client folder** (if new) and the **project folder**, with the correct names.
   - Store the folder URLs on the Company and Project.
   - Set the person's Relationship Stage to opportunity and link them in the project's contact roles.
3. A Notion button can't do this alone, because it can't touch Drive.

**5.2 Draft → Final (the drafting and finalize skills)**
1. **Drafting skill:**
   - Always targets the AI Drafts database by stored ID, never by search.
   - Always sets properties: Project, Type, Audience, Status = draft, Summary, AI.
   - **Edits drafts in place** with find-and-replace or append-at-end (cheap), and refreshes Summary when content changes materially.
2. **Finalize skill:**
   - Creates the Google Doc **in the correct Drive folder the first time.**
   - Names it by Audience (Section 3.3).
   - **Internal finals** carry the Notion draft URL inside the doc.
   - **Client-facing finals do not** (no internal links leak). The link lives only on the Notion side, in Final Link, and an agent finds the draft by querying Notion on that link.
   - Sets Final Link, Status = published and Destination on the draft.
   - Runs a **pre-send check** on client-facing docs: no project IDs, no "draft", no internal links, no leftover comments or suggestions.
3. **After publishing, the Google Doc is the source of truth.**
   - Later changes are small direct edits to the Doc (cheap methods only) or a republish at a version milestone.
   - **Drift between draft and final is accepted.** It happens with any system once a final is edited (JC).
4. **When work happens in the client's workspace:**
   - The draft stays in Notion and the final is delivered into the client's system. Destination records where.
   - A copy is also kept in the project's `delivered` folder, so there's a record of what was sent.
5. **Spreadsheets:** finals are Google Sheets. Cell-range edits are expected to be cheap but are **untested**.
6. **Presentations:** drafted and finalized in **Gamma**. The Notion draft holds the outline, and Final Link points to Gamma.

**5.3 Meeting notes**
- The meeting notes tool produces the transcript, and the close-out is written to **Meeting Notes** with a **Project relation** (two-way) and attendees.
- **Decisions and commitments become Tasks.**
- **The project page shows its meetings automatically.** The project template adds a filtered view.
- High-volume, who-said-what material stays with the project, not with people.

**5.4 Client-sent documents (intake)**
- **Intake is manual drop** (JC's choice): someone drops the file into the project's `client-sent` folder in Drive. Email-attachment intake can come later.
- **Originals are never edited.** Keep the original file name with a date prefix (e.g. `20261008_Q3-budget-v2.xlsx`), because the client will refer to it by its name.
- **A scheduled task lists the folder, which is a cheap call. For each new file it creates a Documents row and reads the file once** to write the Summary and key facts.
- **Later tasks start from the row's summary** and open the file only if needed.
- **Large spreadsheets:** list the sheets first and read only what's needed, or analyze them in code. **Untested.**
- **Restricted files** (e.g. covered by a client's AI rules) still get a row, but with a human-written summary and AI access = restricted. Agents check this property before reading.
- **Work happens on a copy, created in the right folder from the start.**
- **Links to files in a client's own workspace** are registered as links, not copied. Copy only when a point-in-time version is needed.

**5.5 Contracts**
- **Signed PDFs** are manually dropped into the client folder's `00_Contracts` subfolder and registered in **Contracts**.
- **An MSA relates to the Company; a SOW relates to its Project and to its parent MSA.**
- **Views:** unsigned, active, renewing in 90 days, by company.
- **Contracts is its own restricted database** (not a view of Documents), because a filtered view isn't a permission boundary. A legal or finance person can be given Contracts without seeing every client file.
- **Agents never edit signed PDFs.**

**5.6 Invoices and payments**
- **The billing tool is the source of truth for money.** There's no Drive folder for invoices, unless an accountant asks for copies later.
- **Flow:**
  1. An agent drafts the invoice from hours.
  2. A human approves it.
  3. The invoice is created in the billing tool, and its number is logged in the Invoices row.
  4. **A payment webhook** (a small script or automation tool like Make, **not AI**) marks the row paid or overdue.
  5. **A nightly reconciliation script** compares open Notion rows with the billing tool, because webhooks get missed.
- **Money data flows one way.** Only the webhook and reconciliation write amounts or paid status. **Agents never mark anything paid.**
- **Multiple billing tools fit one schema:** Billing System + External ID properties. Each tool gets its own webhook or reconciliation [per firm]:
  - Blue Tusk: Stripe.
  - MOG: QuickBooks + Wise. Wise deposit matching is MOG's known manual pain point (P-009), so reconciliation matters more there.
- **Dashboard views:** unpaid, overdue, paid this month.

**5.7 Touchpoints**
- **Recency is mechanical.** A small script reads email *headers* only (who and when, no content) and updates **Last Contacted** on People. That powers follow-up reminders. No AI, no tokens.
- **Substance is sparse and AI-proposed.** A scheduled task reads threads with prospects or key contacts and **proposes** touchpoints only for important things:
  - first meetings, intros and referrals
  - pricing and scope talks
  - contract events
  - personal details (family, preferences)
  - complaints
  - the latest "what we talked about"
- **These go in an append-only log on the person's page** (appends are cheap), flagged as AI-sourced, and skimmed weekly.
- **Project-specific conversation is never logged to the person.** It belongs to the project (Meeting Notes, Tasks).
- Promote touchpoints to their own database only if cross-person queries are ever needed.
- **Salesforce-style automatic email capture is out of scope for now** (JC: overkill).

### 6. Drive structure (pattern; exact taxonomy decided per firm)
**The folder taxonomy is decided per client.** Blue Tusk designs it from the firm's actual work before suggesting anything specific. The pattern below is what's standard.

```
{Firm} shared drive
├── CONVENTIONS                 ← how to navigate; read first
├── INDEX                       ← client code → client folder ID; project ID → project folder ID → Notion link → status
├── 00_Company/                 ← evergreen: admin, legal templates, finance planning, restricted HR records
├── 01_Clients/
│   └── {CLIENT}_{client-slug}/
│       ├── 00_Contracts/       ← signed MSA, NDA, SOWs (registered in Notion Contracts)
│       └── {CLIENT}-{YYMMDDNN}_{project-slug}/
│           ├── client-sent/    ← originals from the client (registered in Notion Documents)
│           ├── delivered/      ← copies of what went to the client
│           └── (finals as needed)
├── 02_Pipeline/                ← proposal and outreach templates (prospects themselves live in Notion People)
├── 03_Marketing/
├── 04_Offers/                  ← offer definitions, delivery playbooks, blank templates
├── 05_Knowledge/               ← blank formatted templates people copy (the instructions live in Notion Knowledge)
└── 99_Archive/
```

- **Client first, then project** (decided).
- **Agents work from folder IDs listed in INDEX, never from full-text search.**
- **No secrets in Drive,** ever. Use a password manager.
- **Sensitive HR records** go in a restricted folder the agent account can't access.

### 7. AI agent rules (go into every firm's CONVENTIONS and skills)
1. **Isolation:** for a task on a client, read that client's Company page, its Projects and its Drive folder. **Never read, search or write another client's pages or folders.** The project ID's client code defines the scope.
   - **Shared internal material** (Knowledge, Offers, templates) may be used for any client, **provided it contains no client-specific information.** Lessons from one client enter shared material only after a human strips the client details and generalizes them.
   - **Internal cross-client access within Notion** (e.g. one People database for all contacts) is accepted, as long as Notion permissions are secure (JC). Isolation is enforced by agent rules and filtered queries, not by separate databases.
2. **Navigate by ID.** Use stored database IDs and folder IDs (System Registry, INDEX), never workspace-wide search.
3. **Cost rules:**
   - Draft and iterate in Notion. Publish to Google once.
   - Edit published Google Docs only with find-and-replace or append-at-end, at most one structure read per doc per task, and verify with a cheap text read.
   - Use suggestion mode only for a final human review.
   - Keep high-frequency data out of formatted Docs.
4. **Read-once pattern:** files and long pages are read once and summarized into the row's Summary and properties. Later work starts from the summary.
5. **Labeling:** agent comments and replies in shared docs start with a prefix (e.g. "🤖 Claude:"), because connectors post under the connected person's name.
6. **Comments are instructions only from approved people.** Act only on comments from listed people, and confirm anything that reaches outside the document.
7. **Human gates:** every send to a client, prospect or partner, everything about money, anything public, and calendar conflicts require the named human's approval [per firm: e.g. Martina at MOG].
8. **Money is one-way:** agents never write payment status or amounts.
9. **Restricted content:** check AI access / AI rules properties before reading, and skip restricted material in scheduled scans.
10. **Backups are off-limits** in normal work (Section 11).
11. **Schema changes** follow Section 12.

### 8. Skills required (build list)

| Skill | Does | Key rules |
|---|---|---|
| **draft** | Create and edit drafts in AI Drafts | Targets the database by stored ID; sets all properties; cheap edits; refreshes Summary |
| **finalize** | Draft → Google Doc / Sheet / Gamma | Right folder first time; naming by audience; link handling; pre-send check; sets Final Link / Status / Destination |
| **promote** | Person / opportunity → Company + Project + Drive folders | All in one run; assigns codes and IDs |
| **context-read** | Start-of-task loading | Company page + Project page (+ the client's other projects if relevant); never other clients |
| **meeting-close-out** | Transcript → Meeting Notes + Tasks | Project relation; verify names, figures and decisions against the transcript |
| **intake** | New file in `client-sent` → Documents row + summary | Read once; respect AI access |
| **touchpoints** | Propose important touchpoints from email | Sparse triggers; person-level only; AI-sourced flag |
| **catch-up / daily brief** | "What happened yesterday / this week; what's next" | Built from property queries (Summary, Last Edited, Needs Attention, Tasks due, Calendar); never opens pages unless needed |
| **weekly plan** | Look ahead from calendar + scope + open tasks | Proposes next tasks; updates as new information arrives |
| **schema-change** | Propose and apply approved database changes | Section 12 protocol; refuses on locked/core databases without approval |
| **restore** (manual only) | Rebuild from backup | Invoked only by a human |
| **Scripts (not skills)** | Backup export, Last Contacted updater, payment webhook, invoice reconciliation, schema drift check | Deterministic, no AI |

### 9. Permissions and sensitive data
- **Restricted teamspaces** for Contracts and Invoices, and for any HR content in Notion.
- **The agent account** gets **read-only** access to Invoices if the daily brief needs outstanding-invoice totals, and **no access** to Contracts unless a specific workflow needs it [per firm].
- **The Notion connector sees whatever its connected user sees.** Permissions are the real boundary; agent rules are the second layer.
- **The backup repo is private,** with access limited, and client data kept in separate folders within it.
- **For a client firm (e.g. MOG):** decide **whose account owns the system and the backups**, and what happens to Blue Tusk's access and any Blue Tusk copies when the engagement ends. **This is a contract question, not a technical one.**
- **Retention:** ask the firm's accountant or lawyer how long invoices and contracts must be kept [per firm].

### 10. Navigation and user experience (keeping Notion from getting busy)
- **No orphan pages.** Everything is a database row created from a template or a skill.
- **A home page made only of linked views:**
  - needs attention
  - pipeline
  - today / this week
  - recent drafts
  - unpaid invoices (restricted)
  - contracts renewing (restricted)
- **Per-person home template.** Every team member gets one page of linked views filtered to "me": their tasks, meeting notes and attention items, plus a private notes area. One template works for every new hire, with no edits. **Notion is the back end; people only need their home page.**
- **Archive culture:** status-based archiving, with views hiding archived rows. A scheduled skill flags drafts untouched for 30 days as Needs Attention.
- **Sensitive areas** live in restricted teamspaces. Check the firm's Notion plan for what it supports.

### 11. Backup and restore
**Why:** Notion's own safety nets aren't a backup.
- The workspace export is manual, and its emailed link expires after 7 days.
- Notion states an export can't be re-uploaded to recreate a workspace. Relations and formulas come out as flat text.
- Trash and page history are short (one source: trash ~30 days; history ~7 to 90 days by plan) and live inside Notion.

**The design: scripted, incremental, relation-preserving**
- **A small script using the Notion API, not AI,** runs on a schedule (nightly or weekly). It exports pages whose Last Edited is newer than the last run. Zero tokens, and the same result every time. *(An AI pass would cost about 1,250 tokens per page at the size we tested.)*
- **Each page becomes a markdown file with properties as YAML frontmatter** (same format as the vault).
- **Five rules that make relations rebuildable:**
  1. Every file carries its **Notion page ID** plus human keys (client code, project ID).
  2. **Relations are stored as target page IDs plus titles,** with titles written as `[[wikilinks]]` so the backup opens in Obsidian with a working link graph.
  3. A **schema manifest** records each database's properties, types, select options, relation targets and formula/rollup definitions. Rollups are derived, so they're recomputed, not restored.
  4. **Restore runs in passes:** rebuild databases from the manifest → create pages (keeping each old ID on its new page) → re-point relations from old IDs to new.
  5. **Filenames are unique:** `{human-key}_{slug}__{short-page-id}.md`.
- **Destinations:**
  - A **private git repo**, which gives versioned history and diffs.
  - A **dated snapshot in Drive.** Backups are append-only, so Drive's inability to edit markdown doesn't matter.
  - Two vendors means no single point of failure.
- **The git repo is real markdown with in-place edits.** It's a candidate for a future cloud vault (flagged, not decided).
- **Not carried by the markdown:** comments, page history, uploaded files (backed up separately), permissions, some view settings. **Keep a written spec of standard views** in the System Registry.
- **Drive finals** have their own trash and version history (same vendor). Add a periodic copy of the shared drive later. Lower priority, since each final has a Notion draft.
- **Backups invisible to agents:**
  - Store them where the Claude-connected Google account can't see: the git repo, or a separate shared drive that account isn't a member of. Search only covers what the account can access.
  - The backup script writes with its own credentials.
  - INDEX lists no backup locations.
  - Restore is a manual-only skill.
  - Each backup file carries `backup: true` in its frontmatter as a safety net.
- **Restore drills:** a backup never restored is a guess. Run one drill when the real databases exist, then periodically.
- **Interim:** until the script exists, do a **monthly manual workspace export, downloaded the same day.**

### 12. Governance: how the system grows

**12.1 System Registry (current state)**
- Lives in Notion **Knowledge** as entries of type "system". Agents read it constantly and edit it when things change.
- **One page per database:**
  - purpose
  - **owner and approvers**
  - who writes and who reads
  - AI access, sensitivity
  - what the key properties mean
  - relations on both sides
  - which skills and views depend on it
  - **core or not**
  - lock status
- **The relationship table** (Section 4.3), kept current.
- **The database ID table,** so skills never search for a database.
- **The standard views spec** (for restore).
- **The change protocol** (below).
- **It does not copy the schema.** Notion's live schema is the source of truth for names and types. Property descriptions document it. The backup manifest doubles as a **weekly drift check** that flags changes nobody registered.

**12.2 Decision log (history)**
- Dated and append-only, in the vault, linked from the registry. For this design: [[business/projects/internal/product/20261008_ai-native-architecture-decision-log]].

**12.3 Change protocol**
1. **Add a property before adding a database.** Create a new database only when lifecycle, permissions or cardinality differ. A filtered subset is a view.
2. **Don't rename or delete properties or select options.** Add, deprecate, migrate, or rename only with the skill updates in the same change.
3. **Every relation is two-way, named on both sides, with its reason logged.**
4. **Every property gets a description.** Select values are lowercase.
5. **Try it in a scratch copy first.**
6. **Order of work:** registry → schema → skills → backup manifest → views/templates. A change isn't done until all five are.
7. **Sensitive data picks the location:** anything involving money, legal, HR or client confidentiality starts in a restricted teamspace.
8. **Log every change:** date, what, why, who approved.
9. **New-database checklist:** register it (with owner, core yes/no), add property descriptions, add it to the backup manifest, build its views, update affected skills.

**12.4 Who can change the schema**
- **Agents may alter databases when explicitly permitted by the right people (JC).**
- Every change starts as a **proposal row** in the registry: what, why, impact on relations / skills / backup manifest, approver, status.
- An agent acts only on an **approved** row, and only if the approver is on that database's approver list.
- **Two tiers:**
  - **Additive** (new property, new select option): the owner's approval.
  - **Destructive** (rename, drop, type change, relation change): the owner's approval, **plus a fresh backup of that database first, plus the skill updates in the same change.**
- **Afterwards:** relock, update the registry, check the manifest diff, log it.

**12.5 Locks**
- **Every core database is locked** with Notion's database lock. Per Notion documentation and third-party guides, locking blocks adding, editing or deleting properties, select options and database automations, while rows can still be added and edited.
- **Unlock only for an approved change, then relock.**
- **Untested:**
  - Whether the lock stops the connector.
  - Who can unlock (sources conflict: the person who locked it, or anyone with edit access).
  - The connector's schema tool has no lock/unlock option. If the lock does hold against it, only a human can unlock, which matches the approval rule.

**12.6 Deleting databases**
- **Core databases** (listed as core in the registry) can only be trashed in the Notion UI, by a human. Agents refuse and point to the UI.
- **Non-core databases** (e.g. one someone made on their own page or inside a client project): **a clear delete request is enough** (JC). The agent:
  1. Looks the database up in the registry. Not core → continue.
  2. Fetches its schema. **If any relation touches a core database, it's core-adjacent:** stop and ask for the owner's approval.
  3. Deletes it and reports the name, row count, that it can be restored from Notion trash for a limited time, and that it isn't in the backup.
- **Promotion to core:** if a personal database starts to matter (a skill uses it, or a core database relates to it), register it. It then gets locked and backed up.

### 13. Cost model (measured 2026-10-07 and 2026-10-08; estimates at ~4 characters per token)

| Operation | Rough tokens |
|---|---|
| Notion: catch-up query, 3 rows (name, client, status, flag, summary, created) | ~250 |
| Notion: needs-attention query | ~100 |
| Notion: read a full page (~3,600 characters of text) | ~1,250 |
| Notion: find-and-replace / append / property update | tiny (returns page ID only) |
| Google Doc: text read (Drive reader) | ~1x the text (~300 for a 1-page doc) |
| Google Doc: structure read (needed for positional edits) | **~30–100x the text** (~8–10K for a 1-page doc) |
| Google Doc: one-sentence edit with verification | **~20,000** |
| Google Doc: find-and-replace or append-at-end (no read) | small |
| Real `.md` in Drive | can be created and read, **cannot be edited in place** |

**Conclusion:** working drafts in Notion are roughly **15–200x cheaper** than editing Google Docs, depending on whether the result is re-read to verify.

### 14. Implementation order (staging for any firm)
1. **Foundations:**
   - Identity scheme (client codes, project IDs).
   - Drive skeleton + CONVENTIONS + INDEX.
   - Notion **Companies, People, Projects, Tasks**.
   - System Registry with entries for each.
   - **Quick win:** People with Last Contacted / Next Follow-up gives a working CRM and follow-up cadence.
2. **Working layer:**
   - **Meeting Notes, AI Drafts.**
   - Skills: draft, finalize, promote, context-read, meeting-close-out, catch-up.
   - Per-person home template.
3. **Registers:**
   - **Documents, Contracts, Invoices** (restricted).
   - Intake skill, billing webhook + reconciliation.
4. **Knowledge** database (company knowledge and the registry live here from the start).
5. **Resilience:**
   - Backup script + manifest, the first restore drill, locks on core databases, drift check.
6. **Growth:** change protocol in use; touchpoints and weekly-plan skills.

Each stage updates the registry and the backup manifest before it counts as done.

### 15. Tested vs untested

| Item | Status |
|---|---|
| Drive: shared drive create / read, native Docs and Sheets, edit in place, suggestion mode, comment loop, rename, trash | ✅ tested |
| Drive: moving files | ❌ blocked (permission error, even with Manager access) |
| Drive: editing `.md` in place | ❌ not possible with current connectors |
| Notion: create database, create pages, catch-up queries, find-and-replace, append, property updates | ✅ tested (scratch DB "SCRATCH - AI Drafts Test") |
| Notion lock vs connector; who can unlock | ⏳ untested (needs JC to lock the scratch DB) |
| Backup export → restore with relations | ⏳ untested (planned: two related scratch DBs, export, restore into a fresh copy, diff) |
| Uploading Office/PDF files via the Drive connector; reading Word/Excel/PDF (tables, tracked changes) and their cost | ⏳ untested (needs sample files in the Taxonomy Test folder) |
| Google Sheets cell-range edit cost | ⏳ untested |
| Billing webhooks (Stripe, QuickBooks, Wise) | ⏳ untested |
| Notion SQL query limits by plan | ⚠ SQL unlimited only on Business / Enterprise with Notion AI; others share a limit. Use filter-based queries or saved views elsewhere. |
| Notion trash and history retention by plan | ⚠ verify per firm |

### 16. What's fixed vs per firm
- **Fixed (the pattern):**
  - The principles
  - Notion = drafts / Drive = finals
  - The identity scheme
  - The ten-database model and its property conventions
  - Agent rules
  - Backup design
  - Governance
- **Per firm:**
  - Folder taxonomy (decided by Blue Tusk per client)
  - Client codes
  - Billing tool and its webhooks
  - Meeting notes tool
  - Who the approvers are
  - Notion plan and its limits
  - Restricted teamspaces
  - Retention periods
  - Who owns the system and backups
  - Whether one shared database across clients is acceptable to the client (to discuss with Martina)

## Next steps
- [ ] **JC:** discuss with Martina: one shared database across her clients (filter-based isolation), and her Notion plan (Business needed for unlimited SQL and teamspace permissions).
- [ ] **JC:** lock the scratch database in the Notion UI so the lock test can run.
- [ ] Run the backup → restore test with two related scratch databases.
- [ ] **JC:** drop sample Word, Excel and PDF files into the Taxonomy Test folder for the upload and read tests.
- [ ] Confirm client codes (including MAY vs Martina's "MC" for Maycomb).
- [ ] Turn this into MOG's build plan (Phases 0–1) and into a reusable Blue Tusk offering artifact.
- [ ] Delete the scratch Notion database when testing is done.
