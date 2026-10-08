---
title: "AI-Native Operating Architecture — Decision Log"
date: 2026-10-08
tags: [project, strategy, ai]
ai: claude
status: ok
---

# AI-Native Operating Architecture: Decision Log

## Summary
This is the dated, append-only record of every architecture decision behind [[business/projects/internal/product/20261008_ai-native-operating-architecture]]. Each entry says what was decided, why, who decided, and its status. New decisions go at the **bottom**. Superseded decisions stay, marked superseded, with a pointer to the decision that replaced them.

## Context
- Decisions were made by JC with Claude on 2026-10-07 and 2026-10-08, during the MOG AI-first retainer.
- **Statuses:**
  - **Decided:** JC confirmed it.
  - **Accepted:** JC agreed in discussion or proceeded on it without objection.
  - **Open:** not yet decided.
  - **Superseded:** replaced by a later entry.

---

## Content

### 2026-10-07

**AD-001. Google Drive is the file platform (MOG D1).** *Decided.*
Hands-on connector tests passed everything needed:
- Shared drive access
- Native Docs and Sheets
- Edit in place
- Suggestion mode
- The comment loop

Evidence: [[business/projects/internal/product/20261007_google-drive-taxonomy-test-results]].

**AD-002. Folder taxonomy is decided per client.** *Decided (JC).*
There's no standard folder template. Blue Tusk designs each firm's taxonomy from its actual work before suggesting anything specific. The *pattern* is standard; the folders aren't.

**AD-003. Per-client `_ai/` working folder in Drive.** *Superseded by AD-016 and AD-017.*
The original idea was an AI-only folder per client for agent notes, handoffs and rough markdown drafts.

**AD-004. Token cost is a design constraint.** *Decided (JC: "we can't afford the massive token spend constantly updating Google Docs").*
Measured: a Google Doc structure read is ~30–100x the text, and a one-sentence edit with verification costs ~20K tokens. Cheap paths only on Google: find-and-replace, append-at-end, text reads.

**AD-005. Real markdown can't be edited in place in Drive (finding).** *Fact.*
Create and read work. Edit, overwrite and move don't. Same-name create makes a duplicate. Markdown syntax inside a Google Doc doesn't reduce structure-read cost, because cost scales with paragraph count.

**AD-006. Agents can rename and trash but not move files in the shared drive (finding).** *Fact.*
The move failed with a permission error even with Manager access.

**Consequence:** anything an agent creates in Drive must be created in the right folder the first time.

**AD-007. Client first, then project.** *Decided (JC).*
Drive groups by client folder, then project folders inside.

**AD-008. Every client gets a 3-letter code, built into every project ID.** *Decided (JC); code-first recommended.*
- Format: `{CLIENT}-{YYMMDDNN}`.
- Codes are fixed length, unique and never reused.
- Internal work uses its own code (e.g. `BTK`).

Proposed codes for current clients are in the drive restructure note.

**AD-009. Agents may work across a client's projects, never across clients.** *Decided (JC).*
Shared internal material is usable for any client only once client details are stripped out by a human.

### 2026-10-08

**AD-010. Notion is always drafts; Google Docs are always finals.** *Decided (JC).*
- All drafting happens in a Notion **AI Drafts** database, tagged by project and linked to the Drive folder.
- A final is created in Google only when the content is settled or ready to send.
- **Why:** Notion edits are roughly 15–200x cheaper (tested).
- **Bonus:** created and last-edited dates give a time-ordered view across all work.

**AD-011. Notion editing costs (finding).** *Tested.*
- Catch-up query: ~250 tokens for 3 rows.
- Full page read: ~1,250 tokens.
- Find-and-replace, append and property updates return only a page ID.
- Created and Last Edited update automatically.

**AD-012. Every row has a one-line Summary property.** *Decided (JC).*
Queries return properties, so agents catch up without opening pages. Skills must refresh Summary when content changes materially. Paired with a **Needs Attention** checkbox.

**AD-013. Properties mirror vault frontmatter (one open format).** *Decided (JC).*
- title = Name
- date = Created
- tags = Tags
- ai = AI
- status = Status + Needs Attention

Exports become standard markdown notes with YAML frontmatter.

**AD-014. Internal docs carry the Notion draft URL; client-facing docs don't.** *Decided.*
Originally all finals were to carry the Notion URL. That was refined so internal links never leak to clients. For client-facing finals, the link lives only in the draft's Final Link.

**AD-015. One AI Drafts database across clients.** *Accepted (JC); to discuss with Martina.*
JC is fine with one database, with isolation by filtered queries and agent rules rather than separate databases.

**AD-016. Living client and project context lives in Notion.** *Accepted (JC proceeded to backup planning on this basis).*
- Base client context goes on the Company page; project context on the Project page.
- **Why:** it changes constantly (the cheap-edit side), it's internal and candid, it gets queryable summaries, and the people already work in Notion.
- Drive holds only a link.

**AD-017. Backups: scripted export to markdown + frontmatter, relation-preserving.** *Decided (JC).*
- A Notion API script, not AI, does incremental exports.
- Destinations: a private git repo plus a dated Drive snapshot.
- Page IDs, relation IDs, `[[wikilinks]]` and a schema manifest make relations rebuildable.
- Restore runs in passes, with periodic drills.
- Interim: a monthly manual export.

**AD-018. Backups are invisible to agents.** *Decided (JC).*
- Stored where the Claude-connected account can't see them.
- Not listed in INDEX.
- Restore is manual-only.
- Each file carries a `backup: true` frontmatter marker.

**AD-019. Skills enforce the system.** *Decided (JC).*
- A **draft** skill always targets the same database by ID, always sets the right properties, and edits drafts in place.
- A **finalize** skill creates finals correctly.

Further skills are listed in the reference doc, Section 8.

**AD-020. Presentations are drafted and finalized in Gamma.** *Decided (JC).*
Notion holds the outline; Final Link points to Gamma. Google Slides isn't used for drafting.

**AD-021. Hierarchy is Area → Project → Task. Company is a relation from Project.** *Decided (JC).*
- An earlier proposal of Company → Initiative → Project was rejected.
- Area is a single-select (client / internal / admin), named "Area" rather than "Scope" to avoid a clash with scope of work.
- **No sub-projects;** tasks are enough.

**AD-022. Contact roles live on the Project.** *Decided.*
Main contact, secondary contact, decision-maker and stakeholders are relations from Project to People.

**AD-023. Task owners are Notion users (team only).** *Decided (JC).*
The client side relates through the Project's contact roles.

**AD-024. Meeting Notes have a two-way Project relation.** *Decided (JC).*
The project page shows its meetings.

**AD-025. The pipeline lives on People until there's scoped work.** *Decided (JC).*
- People get a Relationship Stage, Last Contacted and Next Follow-up.
- **A Project is created when there is scoped work or a document to write.**
- **The Company is created at promotion,** not before.
- Promotion is a skill (Company + code, Project + ID, Drive folders), because a Notion button can't touch Drive.

**AD-026. Touchpoints come in two tiers.** *Decided (JC).*
- **Recency:** a header-only script updates Last Contacted.
- **Substance:** an AI-proposed sparse log on the person's page, only for important things.
- Project conversations stay with the project.
- Salesforce-style capture is out of scope.
- Internal cross-client visibility in Notion is fine if Notion is secure (JC).

**AD-027. One ID used everywhere; links by URL or ID, never by name.** *Decided.*
- The Project ID lives on the Project. Drafts, notes and tasks relate to it and get the ID and Drive folder by rollup.
- This replaces the typed Project ID used in the first test.

**AD-028. Files are named by audience.** *Decided (JC).*
- **Internal:** `YYYYMMDD_{CLIENT}-{ID}_description`.
- **Client-facing:** a clean title with no date, ID or "draft", set from the start.
- An **Audience** property on drafts tells the finalize skill which to use.
- Draft titles in Notion are the clean titles.
- The finalize skill runs a pre-send check for internal markers.

**AD-029. Client-sent files: manual drop into a project `client-sent` folder + a Documents register.** *Decided (JC).*
- Read once, then summarize.
- Originals are never edited.
- Restricted files get a human summary and AI access = restricted.
- Links to client-workspace files are registered, not copied, by default.

**AD-030. Company knowledge lives in Notion Knowledge.** *Decided.*
- SOPs, guides, template instructions and policies are Notion pages.
- Blank formatted templates people copy live in Drive, linked from the Knowledge page.
- Sensitive HR records go in a restricted Drive folder closed to agents.

**AD-031. Contracts get their own restricted database.** *Decided (JC).*
- Initially folded into Documents, then reversed, because a filtered view isn't a permission boundary and contracts need their own fields.
- Signed PDFs go in the client folder's `00_Contracts`.

**AD-032. Invoices: the billing tool is the source of truth; Notion is the register.** *Decided (JC).*
- A webhook (script or automation tool, not AI) marks invoices paid or overdue.
- A nightly reconciliation catches missed webhooks.
- Agents never mark anything paid.
- Billing System + External ID fit multiple tools: Stripe (Blue Tusk); QuickBooks + Wise (MOG).
- Restricted teamspace; the agent account gets read-only access if the daily brief needs it.

**AD-033. Notion navigability.** *Decided.*
- No orphan pages; everything is a database row.
- A home page of linked views only.
- A per-person home template (their tasks, notes, meetings, attention items).
- Status-based archiving.
- Stale-draft flagging.

**AD-034. System Registry + decision log + change protocol.** *Decided (JC).*
- The registry lives in Notion Knowledge (current state, database IDs, relationships, owners, core flags, views spec).
- The history lives in the vault (this log).
- The registry doesn't copy the schema. Property descriptions document it, and a weekly drift check runs off the backup manifest.

**AD-035. Agents may change schemas with explicit, proper approval.** *Decided (JC).*
- Changes start as a proposal row; agents act only on an approved row, from a listed approver.
- **Destructive** changes also need a fresh backup first and the skill updates in the same change.
- Core databases are **locked** with Notion's lock and unlocked only for approved changes.
- Untested: whether the lock stops the connector, and who can unlock.

**AD-036. Deleting databases: core is UI-only; non-core goes on a clear request.** *Decided (JC).*
- Core = registered as core.
- Non-core databases (personal or project-level) are deleted on a clear delete request, with no extra confirmation.
- The agent still checks the registry and checks relations.
- A non-core database with a relation to a core database is core-adjacent and needs the owner's approval.

**AD-037. The architecture is generalizable.** *Decided (JC).*
- It's built for MOG and becomes the reference for any firm, eventually Blue Tusk itself.
- Per-firm items are marked in the reference doc, Section 16.

### Open (not yet decided)
- **O-1:** Martina's view on one shared database across her clients (AD-015).
- **O-2:** Martina's Notion plan: Business is needed for unlimited SQL queries and teamspace permissions.
- **O-3:** Client codes to confirm, including MAY vs Martina's "MC" for Maycomb.
- **O-4:** Who owns the system and backups for client firms, and what happens to Blue Tusk's access and copies at engagement end (contract question).
- **O-5:** Retention periods for invoices and contracts (per firm, ask the accountant).
- **O-6:** Whether the backup git repo becomes the cloud vault (flagged, not decided).
- **O-7:** Aligning JC's vault to client-first naming (`MOG-26092901_…`).
- **O-8:** Tests pending: the Notion lock vs connector, backup → restore, Office file upload and read cost, Sheets edit cost, billing webhooks.
