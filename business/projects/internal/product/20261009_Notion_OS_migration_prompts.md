---
title: "Notion Legacy to Operating System: Migration Prompts for Notion AI"
date: 2026-10-09
tags: [project, tool, ai]
ai: claude
status: needs-attention
---

# Notion Legacy to Operating System: Migration Prompts for Notion AI

## Summary
Six prompts, run in order, that have Notion AI (1) clear the example data from the Operating System, (2) audit the legacy Operations Master, CRM Master and Blue Tusk Meeting Notes, (3) add the properties the legacy data needs, then (4 to 6) copy the data across with relations intact. The legacy databases stay untouched until everything is verified. Vault content is NOT done by Notion AI (it can't see the vault); Claude copies that in afterwards through the Notion connector.

## Context
- Workspace: the top-level page **Operating System** (was "Operating System (Sandbox)"; renamed 2026-10-09). Spec: [[business/projects/internal/product/20261008_notion-build-spec-sandbox]]. IDs: [[business/projects/internal/product/20261008_notion-sandbox-registry]].
- Legacy sources (all under Growth Home / Blue Tusk Home):
  - Operations Master: `collection://21481bf6-100c-4ace-8f48-8089bc34fc38` (26 projects, 187 tasks; one database, Type = Project or Task)
  - CRM Master: `collection://1d15ea2e-3b9e-4fd7-a13b-8ab14afd7099` (25 companies, 112 people; one database, Type = Person or Company)
  - Blue Tusk Meeting Notes: `collection://33082a6d-029a-8033-844e-000b0898d88a` (60 meetings, 2026-03-27 to 2026-10-09)
- Counts above were queried 2026-10-09 and are the expected totals for verification.
- Decisions baked into these prompts (JC can veto any before running): see "Decisions to confirm" at the bottom.

## Content

### Rules block (paste at the top of prompts 3, 4, 5 and 6)

```
RULES FOR THIS MIGRATION. Follow every one.
1. The legacy databases (Operations Master, CRM Master, Blue Tusk Meeting Notes) are READ-ONLY. Never edit, move, rename or delete anything in them.
2. Copy page bodies in full and verbatim. Do not summarise or rewrite body content. If something cannot be copied (an AI meeting-notes transcript, an uploaded file, comments), say so in the Migration log and keep the Legacy Link.
3. Every new row gets a "Legacy Link" (URL) pointing at its legacy page, and one line in the Migration log (Knowledge row, Type = system, Name = "Migration log: legacy Notion to Operating System", columns: legacy title | legacy URL | new URL | database | notes).
4. Work in batches of 20 rows or fewer. In each database, first create a PILOT of 3 rows, then stop and show me them. Continue only when I say "continue".
5. Relations: set one relation per row at a time, then re-read the row to confirm it saved. After limiting a relation to one page, check the other side did not get the same limit.
6. Do not copy formulas or rollups. Select values are lowercase. Every new property gets a description. Every row gets a one-line Summary that states the current state of the item.
7. Never guess. If a mapping is ambiguous, still create the row, tick Needs Attention, put the reason in Summary, and add the row to a "Review list" page (Knowledge row, Type = system, Name = "Migration review list").
8. Titles are clean human titles. Project titles are "{Project ID} {Project name}". No emoji in names.
9. When finished, report: rows created per database against the expected count, rows flagged for review, anything that could not be copied.
```

### Prompt 1: remove the example data

```
The top-level page "Operating System" (formerly "Operating System (Sandbox)") is now our real workspace. It still contains example data from the build. Remove the example data and nothing else.

1. Find every row whose title or Summary contains "EXAMPLE" (case-insensitive) in these databases: Companies, People, Projects, Tasks, Knowledge, AI Drafts, Meeting Notes, Handoffs, Documents, and the restricted Contracts and Invoices.
2. Do NOT touch: the Knowledge rows for the System Registry, every "Registry: ..." page, "How to use this system", "Getting started", the strategy pages (Type = guide, Tags include strategy), any template, any view, Home, Clients, All work, My page. If one of those contains the word EXAMPLE, list it but leave it.
3. Reply FIRST with a table: database | row title | why it matched. Do not delete anything until I reply "go".
4. After "go": move the rows to trash (never permanent delete). Then report the row count per database and confirm no example rows remain.
5. In the System Registry and the registry pages, remove or reword mentions of "sandbox" and "EXAMPLE". Add a Change log row: today's date | "Removed example data; workspace is now the live system" | "Sandbox build complete; moving to real data" | JC.
6. If "SCRATCH - AI Drafts Test" or "SCRATCH - Skills Test" still exist, list them but do not delete them.
7. Check that Home, Clients, All work and My page still load, and tell me which views are now empty.
```

### Prompt 2: audit the legacy databases (read-only)

```
Audit three legacy databases before we migrate them. This is READ-ONLY: change nothing in them, and create exactly one new page: a Knowledge row (Type = system, Audience = admins, Status = draft) named "Migration plan: legacy Notion to Operating System".

Sources:
- Operations Master (projects and tasks in one database; Type = Project or Task)
- CRM Master (people and companies in one database; Type = Person or Company)
- Blue Tusk Meeting Notes

Put these sections in the page:

A. Fill rates. For each legacy database and each property: how many rows have a value. Include page-body size: how many rows have an empty body, a short body, a long body.
B. Body contents. How many pages contain: AI meeting-notes blocks or transcripts, uploaded files or images, embedded databases or linked views, sub-pages, comments. List the page titles for each (first 20 of each).
C. Duplicates and quality. In CRM Master: people or companies with the same name or the same email. Rows with no name. In Operations Master: tasks with no Parent Project; projects with no Client. Relations that point at rows that no longer exist.
D. The CRM cadence. Open the formulas "Next Touch", "Effective Last Touch" and "Touch Signal" in CRM Master. Write down in plain English the cadence (days) per Category and how they are calculated.
E. People who are Blue Tusk team members (Category = Blue Tusk, or Project Lead / Responsible values). List them. Team members are Notion users in the new system, not People rows.
F. Companies. A table of all 25 companies: name | Category | Status | number of linked projects | number of people | proposed Client Code (3 capital letters, unique) | proposed Type for the new system (client / partner / vendor / internal / prospect). Companies with at least one project get a code. Companies with no project get NO code (they get one when promoted). Use these codes where they apply: Blue Tusk = BTK, Madrid Operations Group = MOG, Maycomb Capital = MAY, Ruthless For Good = RFG, LendForGood = LFG. Propose the rest and mark them "proposed".
G. Projects. A table of all 26 projects: legacy title | Track | Status | Start Date | proposed Project ID | proposed Name | proposed Area | proposed Stage. Rules:
   - Project ID format is {CLIENT}-{YYMMDDNN}.
   - If the legacy title starts with 8 digits (for example 26092901), keep them: 26092901 for Madrid Operation Group becomes MOG-26092901.
   - If it starts with 6 digits (260701 to 260799, internal quarterly projects), the new ID is BTK-YYMM01NN: 260701 becomes BTK-26070101 and 260799 becomes BTK-26070199.
   - Cause Crazy uses the date 25122101 (the existing Drive and vault folder is dated 20251221): CCZ-25122101 (propose the code).
   - Ghost.Ops uses 26050701: propose GHO-26050701.
   - Any other project: use its Start Date as YYMMDD plus 01, 02 and so on for same-day collisions; if it has no Start Date use its Created time and mark the row "date guessed".
   - Proposed Name: the legacy title with the leading ID, any leading "NN_" prefix, and a leading "{client name}-" removed.
   - Area: External becomes client; Internal becomes internal, except names containing Admin or Finance become admin, and "Non-Business" becomes admin and flagged.
   - Stage: 02_doing becomes active (internal ones become ongoing); 03_blocked becomes active and flagged; 05_complete_delivered becomes done; Canceled becomes lost; Archived becomes archived; empty status becomes proposal for external projects and ongoing for internal ones, and is flagged.
H. Everything that does not fit. List legacy properties that have data but no home in the Operating System (for example Industry, Website, Location, Time Zone, Value Tier, Estimated Value/Year, Mutual Connections, Channel, Draft Message, Draft Status, Outreach Tier, Revenue fields, Priority, Role, Tags, Project Type, Completion Date), each with its fill rate.
I. Decisions for JC. A numbered list of anything ambiguous.

Report when done with the link to the page and the five most important findings.
```

### Prompt 3: schema additions (run after JC reviews the audit)

```
Make additive schema changes to the Operating System databases so the legacy data has a home. ADD ONLY. Do not rename or delete any property or option. Follow the change protocol: every property gets a description, select options are lowercase, every relation is two-way and named and described on both sides.

Gate: for every property below that comes from a legacy database, first count the non-empty values in the legacy database. If the count is 0, skip it and tell me. Add it only if at least one row has data.

ALL FIVE of Companies, People, Projects, Tasks, Meeting Notes:
- "Legacy Link" (URL): Link to the original page in the legacy Notion database. Remove after migration is verified.

COMPANIES
- Type: add the option "prospect" (organisation we are talking to but have no project with; gets a Client Code when promoted).
- Add if filled in legacy: "Website" (URL), "Industry" (text), "Location" (text), "Time Zone" (select, same values as CRM Master but lowercase where they are words).

PEOPLE
- Relationship Stage: no new options.
- Source: add the options "warm reconnection", "linkedin", "client".
- Add if filled: "Category" (select, the 10 CRM Master Category values, lowercase), "Outreach Tier" (select: active, sprint only, never), "Value Tier" (select: high, medium, low), "Channel" (select: email, linkedin, text, call, in person), "Draft Message" (text), "Draft Status" (select: drafting, ready to send, sent), "Date of First Contact" (date), "Important" (checkbox), "Industry" (text), "Location" (text), "Time Zone" (select), "Website" (URL), "Mutual Connections" (text), "Lesson Learned" (text), "Estimated Value Per Year" (number, US dollars).
- Add the relation "Referred By" (People to People, limit one) with the reverse "Referrals Given" (many).

PROJECTS
- Add if filled: "Project Type" (select: ai and automation advisor, one off automation, ai rebuild, other), "Completed Date" (date), "Priority" (select: high, medium, low), "Tags" (multi-select, the legacy tag values lowercase).

TASKS
- Status: add the option "idea".
- Add if filled: "Role" (select, the legacy Role values lowercase), "Start Date" (date), "Completed Date" (date).

MEETING NOTES
- Meeting Type: add the option "connection".
- Add: "New CRM People" (text): Scratchpad for people mentioned or attending who are not yet in People. Add names, emails, titles and context for AI to turn into People rows later.

CONTRACTS (restricted area)
- Add: "Monthly Retainer" (number, US dollars), "One-Time Fee" (number, US dollars), "Retainer Months" (number), "Revenue Model" (select: one-time fee, hybrid, non-revenue, monthly retainer).
- Do not add these to Projects: money stays in the restricted area.

Then: update the registry page for each database touched, add a Change log row per database (today's date | what was added | "needed to migrate legacy Notion data" | JC), and update the Relationships table for the new Referred By relation. Report what was added and what was skipped.
```

### Prompt 4: migrate Companies and People

```
[Paste the RULES block first.]

Migrate CRM Master into Companies and People.

COMPANIES: every CRM Master row with Type = Company (expected: 25), using the company table approved in the Migration plan (section F).
- Name = Name. Client Code = approved code (blank for companies with no project). Type, Status: from the approved table; Status = past if Category is Past Client or legacy Status is Archived; paused if legacy Status is Dormant; otherwise active.
- Owner = JC. Properties added in the schema step (Website, Industry, Location, Time Zone) = the legacy values.
- Page body: use the Company template, and put the entire legacy page body (including any Touch Log) under the "History" heading, verbatim. Put the legacy "Personal Notes" under "Overview".
- Summary = one line from the body or notes.

PEOPLE: every CRM Master row with Type = Person (expected 112), EXCEPT team members found in the audit (section E; expected 1). List the excluded team members in the Migration log with the reason.
- Name, Email, Phone, LinkedIn, Role / Title becomes Title. Company = the matching new Companies row (match by legacy relation, not by name). Leave empty where the legacy row had no company.
- Relationship Stage: Category Active Client or Status Converted becomes client; Category Past Client becomes past client; Category Ignore becomes archived; legacy Status Archived becomes archived; Dormant becomes dormant; Active Pipeline becomes opportunity; Nurturing becomes in conversation; empty becomes identified. First matching rule wins, in that order.
- Last Contacted = the later of legacy "Last Touch" and the date of the most recent linked legacy meeting (this is what "Effective Last Touch" did).
- Next Follow-up = Last Contacted plus the cadence (days) for that person's Category as written in section D of the Migration plan, ONLY for people whose Outreach Tier is Active (or empty). Leave it empty for Sprint Only and Never. Put the calculation rule in the Change log so it can be re-run later by script.
- Source: Cold Outreach becomes outreach; Warm Reconnection becomes warm reconnection; Referral becomes referral; LinkedIn becomes linkedin; Event becomes event; Client becomes client.
- All other added properties = the legacy values.
- Page body: People template. The entire legacy page body, including the Touch Log, goes under "Touchpoints", verbatim. "Personal Notes" goes under "About". Do not rewrite anything.
- After all rows exist, second pass, one relation at a time: set "Referred By" from the legacy Referred By.

Pilot first (3 companies, then 3 people), then stop.
```

### Prompt 5: migrate Projects, Tasks and the money fields

```
[Paste the RULES block first.]

Migrate Operations Master into Projects, Tasks and Contracts.

PROJECTS: every row with Type = Project (expected 26), using the approved table in the Migration plan (section G).
- Project ID, Name (title is "{Project ID} {Name}"), Area, Stage: from the approved table.
- Company = the new Companies row for the legacy Client.
- Owner = JC unless the legacy Project Lead is a different Blue Tusk team member (then flag it). Stakeholders = legacy Team (People rows only). Do NOT set Main Contact or Decision Maker: they were not tracked, and we do not guess.
- Start Date = Start Date. Target End = Due Date. Completed Date = Completion Date.
- Project Type, Priority (P0 and P1 become high, P2 medium, P3 low), Tags: carry across if added.
- If Doc Link is a Google Drive folder URL, put it in Drive Folder. Otherwise put Doc Link and SOP as links in the page body under "Scope".
- Blocked projects (03_blocked): Needs Attention ticked, and say why in Summary.
- Page body: Project template; the legacy body goes under "Scope" verbatim; legacy "Notes" under "Where things stand / Current state". Summary on every row.

TASKS: every row with Type = Task, plus the one row with an empty Type that has a Parent Project (expected 187 in total).
- Name; Project = the new Projects row for the legacy Parent Project; Owner = legacy Responsible if it is a Notion user; Due = Due Date; Summary = legacy Summary.
- Status: XX_idea becomes idea; 00_date_set becomes to do; 01_do_now becomes to do; 02_doing becomes doing; 03_blocked becomes waiting; 04_complete_not_delivered becomes done (add "complete, not delivered" to Summary); 05_complete_delivered becomes done; Canceled becomes cancelled; Archived becomes archived.
- Priority: P0 and P1 become high, P2 medium, P3 low.
- Role, Start Date, Completed Date: carry across if added.
- Body copied verbatim. Legacy "Notes" appended to the body under a heading "Notes". Doc Link and SOP become links at the top of the body.
- The one row with an empty Type: flag for review.

CONTRACTS (restricted area): for every project that has a Monthly Retainer, One-Time Fee or Revenue Model value, create ONE Contracts row.
- Name = "{Project ID} SOW (migrated terms)". Type = sow. Company and Project = the new rows. Monthly Retainer, One-Time Fee, Retainer Months, Revenue Model = the legacy values (Revenue Model lowercase). Value = One-Time Fee + Monthly Retainer x Retainer Months.
- Status: project Stage active or ongoing becomes active; done becomes expired; proposal or discovery becomes draft; lost becomes terminated.
- Body: "Migrated from Operations Master. No signed copy is attached. Replace with the real contract when it is filed in 00_Contracts."
- Do NOT copy the legacy formulas (Contract Value, Active MRR, YTD Revenue, Project Health, Days Remaining, Completion). In the Migration plan, list which dashboard views used them.

Pilot first (3 projects, then 3 of their tasks), then stop. Do projects, then tasks, then contracts.
```

### Prompt 6: migrate Meeting Notes, then verify

```
[Paste the RULES block first.]

Migrate Blue Tusk Meeting Notes into the Operating System's Meeting Notes (expected 60).

- Name = Name (keep as is). Date = Date of Meeting. Requires Follow-up and Followed Up = the legacy checkboxes.
- Meeting Type: internal, client, prospect, connection become lowercase equivalents. Empty (4 rows): leave empty and flag.
- Project = the new Projects row for the legacy Project. If a meeting has more than one project, link the first and write the others into Summary and flag it.
- Attendees = the new People rows for the legacy Attendees. Team Attendees = JC on every meeting.
- If the legacy meeting had a Company but no Project, write the company name into Summary and flag it. (There is no Company property on Meeting Notes in the new system: the company comes through the Project.)
- "New CRM People" = the legacy text.
- Page body: copy verbatim, including the AI meeting-notes summary, action items and transcript. Check this on the 3 pilot meetings: open the legacy page and the new page side by side and tell me if anything is missing. If the transcript cannot be copied, keep the Legacy Link and note it in Summary.

Pilot first (3 meetings), then stop.

THEN VERIFY, once all migrations are done:
1. Counts: Companies 25, People 111 or 112 minus excluded team members, Projects 26, Tasks 187, Meeting Notes 60. Report each count against expected.
2. Relations: every task has a Project; every project has a Company; every person who had a Company in the legacy has one now; every meeting has the same number of attendees as before (list any that differ).
3. Spot-check 10 random rows in each database against the legacy page (title, key properties, body length).
4. List every row with Needs Attention ticked and the reason.
5. Update the Migration log, the registry pages and the Change log. Update the Knowledge quick reference ("How to use this system") if how people use the system changed.
6. Do NOT delete, archive or rename the legacy databases yet.
```

### Decisions to confirm (these are baked in above)
1. **Companies without projects are migrated** as Type = prospect with no Client Code (11 companies, e.g. The Injury Specialists, DR Injury Law). The architecture said Companies are only created on promotion, but dropping them would orphan their people. Codes are assigned at promotion.
2. **Money fields go to the restricted Contracts database,** not Projects (architecture Section 5.5: contract value lives on the restricted row). Cost: Contracts will hold "migrated terms" rows that are not signed contracts. Alternative: add the fields to Projects.
3. **Project IDs keep your existing numbers** with a client code in front (for example 26092901 becomes MOG-26092901). Codes for Capital Financing, Neighborworks, Cause Crazy and the older proposal clients are proposals only.
4. **Internal quarterly projects** (260701 to 260799) become BTK-26070101 to BTK-26070199 (day set to 01).
5. **Task statuses:** XX_idea gets its own option "idea"; 01_do_now collapses into "to do" (the "do now" signal is lost).
6. **Blocked projects** become active with Needs Attention ticked (the new system has no blocked stage).
7. **The Blue Tusk team-member row in CRM Master** is not migrated as a person (team members are Notion users).
8. **Legacy stays untouched** until verification passes; each new row has a Legacy Link, removed afterwards.

## Next steps
- [ ] JC: run Prompt 1 (example data removal), then Prompt 2 (audit), and review the Migration plan page.
- [ ] JC: approve or change the codes and the decisions above, then run Prompts 3 to 6, one at a time.
- [ ] Claude: query the new databases after each prompt and compare counts against the expected totals.
- [ ] Claude: after Notion-to-Notion migration is verified, copy the vault into Notion through the connector (separate spec).
- [ ] Update the build spec to v2.2 with the new properties once Prompt 3 has run.
