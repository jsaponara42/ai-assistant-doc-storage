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

**AD-016. Living client and project context lives in Notion.** *Decided (JC, 2026-10-08).*
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

**AD-038. Project folders get an `in-progress/` folder.** *Decided (JC).*
- A deliverable lives there once it's in its final format but not yet final and sent: formatting, client-ready polish, internal review, or anything that has to be built in Google (Sheets, layout-heavy docs).
- **Flow:** draft in Notion (cheap) → the finalize skill creates the Google file in `in-progress/` → it's sent → it becomes the record in `delivered/`.
- **Constraint (AD-006):** agents can't move files in the shared drive. Getting a file from `in-progress/` to `delivered/` is either:
  - **a human drag in the Drive UI** (keeps the link and ID), or
  - **an agent copy** into `delivered/` (new ID; the copy is the record of exactly what was sent), with the in-progress file then trashed or left in place.
  Which one is still **open (O-9)**.
- **Naming:** files in `in-progress/` already use their audience-correct name (AD-028), so nothing needs renaming at send time.
- **AI Drafts Status gains a step:** draft (Notion) → in progress (Google file exists in `in-progress/`) → sent / published.

**AD-039. Backup is an ongoing paid offering.** *Decided (JC).*
The scripted, relation-preserving backup and restore (AD-017), with drills and drift checks, is a recurring service. It also gives Blue Tusk ongoing stickiness with each client.

**AD-040. Feature additions are Blue Tusk's ongoing role.** *Decided (JC).*
- Because each build is customized, Blue Tusk is the natural partner for any new features a client wants.
- The governance layer (registry, change protocol, approved schema changes) is the mechanism. New features go through it, with Blue Tusk as the proposer and implementer.

**AD-041. A simplified version becomes a free lead magnet.** *Decided as direction (JC); content to be designed.*
The principles and the shape of the system are given away; the build, customization, backup and governance stay paid. This matches the free-tier pattern in [[business/projects/internal/product/20260818_File_Taxonomy_Free_Tier_Principles]].

**AD-042. Context handoffs: a Handoffs core database plus a "Where things stand" section on each Project.** *Decided (JC).*
- **Person and session history:** an 11th database, **Handoffs**, with one row per working session (project relations, Summary, done / open / next, Written By = person or agent). **Append-only.** It's a timeline, which overwritten handoff notes lose. **Core database** (registered, locked, backed up).
- **Project current state:** a fixed "Where things stand" section on each Project page, **rewritten** each session so it stays short.
- **Recent activity is computed,** not written: Meeting Notes, AI Drafts, Tasks and Handoffs sorted by Last Edited.
- **One handoff skill writes both:** one Handoffs row plus a rewrite of each touched project's section. A **resume** skill reads them back with property queries only.
- **Known limit:** "Last Edited By" shows whoever connected the agent, so agent edits look like the person's. That's why Handoffs carry an explicit Written By property.
- This replaces the vault's `xx_context-handoff.md` pattern inside client systems. The vault keeps its own until a vault migration (O-6, O-7).

**AD-043. Skills use the open Agent Skills format (finding and decision).** *Tested; decided (JC).*
- Skills are a folder with a `SKILL.md` (frontmatter `name` and `description`) plus optional supporting files, per agentskills.io. Notion, Claude, Codex, Cursor, Gemini and others read it.
- **Tested 2026-10-08:** the skill `catch-up`, written as a Notion skill page, downloaded ("Download for local agents → Claude Code") as a clean folder: `SKILL.md` with only name and description in the frontmatter, the body unchanged, and a file attached to the page's Files property (`CONVENTIONS.md`) bundled alongside it.
- Notion's per-agent download options (Claude Code, Codex, Cursor, Gemini, Grok Build) appear to differ only in where the folder lands locally. Only the Claude Code download was inspected.
- **Consequence:** skills are portable between tools at no cost. Leaving Claude or Notion doesn't strand them.

**AD-044. Claude doesn't discover Notion-hosted skills on its own (finding).** *Tested.*
- With the skill enabled in Notion's Library ("Enable for me"), it still didn't appear in Claude's skill list or in Notion search through the connector. Claude could read it only by page ID.
- Enabling a skill in Notion turns it on for **Notion AI**. Notion AI picking it up from a plain prompt is untested.

**AD-045. The skills master is a private git repo.** *Decided (JC).*
- One private repo per firm, laid out as a Claude plugin marketplace (`.claude-plugin/marketplace.json`, `plugins/{plugin}/skills/{skill}/SKILL.md`). Scripts go in `scripts/`, never a top-level `bin/` (Claude org sync rejects it).
- **All edits happen in the repo;** deployed copies in Claude and Notion are never edited directly.
- **Why git, not Notion, as the master:** versioned history, review before changes go live, and every tool can read it. Claude's official sync reads from GitHub. Notion's official sync (`notion-skills-github-sync`) only runs Notion → GitHub, and Notion's public API only documents downloading skills.
- **Alternative considered:** author in Notion and mirror to git with Notion's sync. It's simpler for people who work in Notion and native for Notion AI, but has no review step and takes two hops to reach Claude. It stays an option for a client whose team authors skills in Notion.

**AD-046. Skills sync regularly from the repo to each tool.** *Decided (JC).*
- **Claude, Team or Enterprise:** organization sync from GitHub, automatic on every push to the default branch. **MOG is on Team**, so this works for Martina.
- **Claude Code:** the repo registered as a plugin marketplace (works on any plan).
- **Claude, Pro chat:** manual upload per skill. **Blue Tusk is on Pro**, so JC's chat copies are uploaded by hand until Blue Tusk moves to Team. Pro upload support is unverified.
- **Notion AI:** a one-way deploy from the repo after each merge (untested, O-12). It may need to be an agent-run step, since the public API documents no upload.
- **Other or local agents:** clone the repo.
- **A scheduled drift check** compares deployed copies with the repo (Notion plugin `version_id` helps) and flags edits made outside it.
- Change flow: branch → review → merge → automatic Claude sync → Notion deploy and manual uploads → version bump and registry update.

**AD-047. Skills are written to be tool-agnostic.** *Decided.*
- Instructions describe the job, not a vendor's interface.
- Each skill has a **Surface** line (Notion-only / needs connectors / needs scripts) and a **Requires** section with a fallback.
- No hard-coded IDs; skills read the System Registry and INDEX.
- Deterministic work stays in scripts the skill calls.
- Plain markdown only.

**AD-048. Skills are registered.** *Decided.*
Each skill gets a System Registry entry (name, version, surface, databases it reads and writes, owner), and the repo itself is listed there. The skills repo is its own versioned master and isn't part of the backup repo.

**AD-049. Navigation is built from views, not folders.** *Decided (JC).*
- Concern raised: a file system lets you see everything at once; Notion spreads content across databases and pages.
- Answer: Project pages act as folders (a standard template of linked views filtered to the project); an "All work" view of AI Drafts grouped by client then project; a short sidebar hub (Home, Clients, Knowledge, personal page); and find-by-ID using client codes and project IDs.
- Known limits: database-row breadcrumbs show the database, not the project; one view can't combine databases.
- Reference doc Section 10.1.

**AD-050. The literal folder tree lives only in the backup repo.** *Decided (JC).*
The nightly backup export is organized by client, project and type, which gives a real file tree with wikilinks. Most people won't use it, so it stays in the GitHub backup repo and isn't promoted to users. Agents still can't see it (AD-018).

**AD-051. Training and a quick reference page live in Notion Knowledge.** *Decided (JC).*
- Training is a first-class part of the system and includes SOPs. Knowledge gains Type = training and Type = quick-reference.
- Each firm gets one "How to use this system" quick reference page: where things live, how to find anything (including find-by-ID as a core tip), naming rules, agent rules and human gates, resume and handoff, how to request a change.
- Linked from Home and every person's page; first read for new hires.
- The change protocol's order of work now ends with updating the quick reference and training when a change affects how people use the system.

**AD-052. Project titles start with the Project ID.** *Decided (JC).*
- Format: `{Project ID} {Project name}`, e.g. `ACM-26100201 Operations Build`. The one exception to clean titles (plus automatic Meeting Notes titles).
- **Why:** a Notion relation shows the related page's title, so every draft, task and meeting shows its project's ID. It also makes find-by-ID reliable.
- The Project ID property stays the official value; an **ID Match** formula flags drift. A template can't fill the ID, so the creator (later the promotion skill) types it.

**AD-053. The Notion half is built by Notion AI from a phased spec.** *Decided (JC); sandbox built 2026-10-08.*
- JC's own workspace got a sandbox with example data, built from [[business/projects/internal/product/20261008_notion-build-spec-sandbox]] in three phases. Notion AI's feedback produced spec v2, and its test answers v2.1.
- The spec is the reusable build artifact for every firm (MOG next). Each build ends with manual steps and a done-when checklist.
- Next: migrate JC's active work into it with a separate migration spec.

**AD-054. Findings from the sandbox build.** *Tested 2026-10-08.*
- **Agent queries can't read formulas or rollups** in bulk, so anything agents filter on must be a base property or relation (agent rule added).
- **Search** finds project IDs in titles and in text properties, but not in URL properties.
- **Notion AI can't lock or unlock databases.** Whether a lock stops agent schema changes is still pending (O-8).
- **Created By / Last Edited By show the person,** confirming the AD-042 limit.
- **Notion AI didn't auto-load the enabled catch-up skill;** it found it by searching. This extends AD-044: neither Claude nor Notion AI reliably picks up a Notion-hosted skill on its own. Skill descriptions name their triggers plainly, and the registry must list database and data source IDs.
- **Meeting notes:** per Notion's docs, the default meetings database receives new AI and Calendar meeting notes; Project and follow-up fields aren't filled automatically (options to test).
- **Plan:** Notion AI couldn't see JC's workspace plan; no teamspaces were visible.

### Open (not yet decided)
- **O-1:** Martina's view on one shared database across her clients (AD-015).
- **O-2:** Martina's Notion plan: Business is needed for unlimited SQL queries and teamspace permissions.
- **O-3:** Client codes to confirm, including MAY vs Martina's "MC" for Maycomb.
- **O-4:** Who owns the system and backups for client firms, and what happens to Blue Tusk's access and copies at engagement end (contract question).
- **O-5:** Retention periods for invoices and contracts (per firm, ask the accountant).
- **O-6:** Whether the backup git repo becomes the cloud vault (flagged, not decided).
- **O-7:** Aligning JC's vault to client-first naming (`MOG-26092901_…`).
- **O-8:** Tests pending: the Notion lock vs agent schema change (JC locks Projects in the sandbox, then Notion AI tries to add a property), backup → restore, Office file upload and read cost, Sheets edit cost, billing webhooks, meeting-note autofill for Project and follow-up. *(Notion AI using an enabled skill: tested, not auto-loaded, AD-054.)*
- **O-9:** How a file gets from `in-progress/` to `delivered/`: human drag (keeps the link) or agent copy (new ID, exact record of what was sent).
- **O-10:** What the free lead magnet includes vs what stays paid (AD-041).
- **O-11:** Who owns each client's skills repo (Blue Tusk's GitHub or the client's), tied to O-4. For MOG: confirm the Owner on Martina's Claude Team plan, who connects the Claude GitHub App.
- **O-12:** Test the git → Notion deploy: upload a skill folder that includes a script via the Notion connector, confirm it arrives intact and that Notion AI uses it. Decide whether the deploy can be a script or must be an agent-run step.
- **O-13:** Whether Blue Tusk moves to a Claude Team plan for automatic skill sync, and confirming that Pro supports manual skill upload in the meantime.
