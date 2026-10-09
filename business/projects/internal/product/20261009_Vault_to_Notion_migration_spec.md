---
title: "Vault to Notion Migration Spec"
date: 2026-10-09
tags: [project, tool, ai, pkm]
ai: claude
status: needs-attention
---

# Vault to Notion Migration Spec

## Summary
How the Obsidian vault gets copied into the Notion **Operating System**, so JC can stop using the vault. Claude does the copy through the Notion connector, using the vault MCP to read notes (Notion AI can't see the vault). The approach follows [[business/projects/internal/product/20261009_Notion_migration_lessons_learned]]: inventory and decisions first, then a pilot, then batches with a log, then verification. The vault is **copied, not moved**. It stays intact as a frozen archive until the Notion backup script exists and a restore drill has passed.

## Context
- Target: top-level page "Operating System". Data source IDs: Knowledge `ea98a02b-12bc-40c4-8594-c9c32258464c`, AI Drafts `d8ce42ea-1a58-4bfe-b65a-d01037c59942`, Handoffs `ce596e39-248c-452c-ad3b-d8d99b4461ac`, Projects `0ac1daaa-95d2-41dc-8aef-44b1df153a21`, Companies `749074dd-9d7d-4009-8b47-841bb80d51fc`, Tasks `5c9d16fa-572b-469d-9aa1-79dfdf92e171`.
- Legacy Notion migration is done and verified (2026-10-09). Knowledge already holds 15 strategy pages copied from the vault/Drive earlier. Those are checked for duplicates before copying anything with the same subject.
- Live target schema checked 2026-10-09. Gaps: Knowledge has no Type for ideas or research, no Department for marketing or product, and no property for the original date (Created can't be backdated) or the vault path.

## Content

### 1. What gets copied where

| Vault content | Notion destination | Properties |
|---|---|---|
| `business/projects/client-projects/{ID}_{client}/` briefs, workflow maps, roadmaps, plans, hire references | **AI Drafts**, Project = matching project | Type: report (briefs, maps, roadmaps) or document; Audience: internal unless it was sent; Status: published if a client version was delivered, otherwise archived |
| `xx_context-handoff.md` (per project) | **Project page → "Where things stand"** (rewritten from it) + **one Handoffs row** "Imported from vault handoff" (Written By = claude) | Handoff body = the note verbatim |
| `xx_Project_Learnings.md` | **Project page**, new heading "Learnings" (verbatim) | — |
| `xx_howies_wants.md`, client preferences | **Company page → "Preferences"** | — |
| `xx_outstanding-questions.md`, `xx_pending-deliverable-revisions.md` | **AI Drafts** (Type document, Status draft) on the project, plus one Task per still-open item | Task Status to do; flagged for JC to confirm still open |
| `business/projects/internal/product/` (architecture, decision log, build spec, offering stack, taxonomy) | **Knowledge**, Type guide or system, Department product | Build spec + decision log = system; the rest = guide |
| `business/projects/internal/google-drive-restructure/` (playbook, script, run log, taxonomy) | **Knowledge**, Type guide (playbook, script) / system (Blue Tusk run log) | Script kept in a code block |
| `business/projects/ghostops/` | **AI Drafts**, Project GHO-26050701 | Type document |
| `business/projects/internal/sales-call-prep/` (prospect call briefs) | **AI Drafts**, Type report, Project = the client's project if one exists (RFG brief → RFG-26073101, Sync Research → SRG), otherwise BTK-26070102 Sales Q4 | Company named in Summary |
| `business/SOPs/` | **Knowledge**, Type sop (SOP-FORMATTING-GUIDE → template-instructions) | Department sales / delivery |
| `business/ideas/` | **Knowledge**, Type **idea** (new) | Status active |
| `business/research/`, `business/projects/internal/20260617_Quick_SOP_Creation_Guide.md` | **Knowledge**, Type **research** (new) / guide | — |
| `business/marketing/offers/` | **Knowledge**, Type guide, Tag strategy (same as the 15 strategy pages) | Department **marketing** (new) |
| `business/marketing/writing/post-*.md` | **AI Drafts**, Type post, Project BTK-26070101 Marketing Q4 | Status: published if posted, else draft (default draft, flagged if unknown) |
| `business/marketing/writing/` WRITING-STYLE, CONVENTIONS, LinkedIn idea list | **Knowledge**, Type guide (style, conventions) / idea (post ideas) | Department marketing |
| `business/marketing/instagram-content-pipeline/`, `materials/` | **AI Drafts** (scripts, one-pager) on Marketing Q4; strategy note → Knowledge guide | — |
| `business/sales/` (call flows, email sequences, outbound SOPs, prompts) | **Knowledge**: SOPs → sop; sequences, call flows, prompts → template-instructions | Department sales |
| `business/ABOUT-BLUE-TUSK.md` | **Company page "Blue Tusk" → Overview** (verbatim) | — |
| `tasks/` open task files (2 RFG tasks, 1 AI task) | **Tasks** on the matching project | Status to do, flagged to confirm |
| `xx_needs-categorization/` (4 notes) | Sorted one by one per this table; personal ones follow decision 1 | — |
| `personal/` | **Decision 1** | — |

### 2. Not copied
- **`_fit/`**: an older copy of the vault (March to April). Claude checks each file against its newer copy first. Anything that exists only in `_fit/` is listed for JC, not silently skipped.
- **Vault system files**: `CONVENTIONS*.md`, `INDEX.md`, `README.md`, `CLIENT-PROJECTS.md`, `XX_personal-templates/`, `TASK-LOG.md`, `COMPLETED-TASKS.md`, `PERMANENT-NOTE.md` placeholders. These describe the vault itself and stay with the archive.
- **`business/SKILLS/`**: skills go to the private skills repo (architecture Section 8.1), not Notion.
- **`xx_needs-categorization/_archived/`**: already re-filed elsewhere (checked per file; anything unmatched is listed).
- **`20261008_notion-sandbox-registry.md`**: superseded by the System Registry in Notion. Its IDs are checked against the registry, then it isn't copied.
- **Non-markdown files** in the client `SOPs/`, `call-prep/` and `client-facing-deliverables/` folders. The vault MCP can't see them. They belong in Drive, not Notion. Checking them needs folder access on JC's Mac.

### 3. Schema additions (additive only; JC approves, then Claude applies and logs)
- **Knowledge, Type:** add `idea`, `research`.
- **Knowledge, Department:** add `marketing`, `product`.
- **Knowledge and AI Drafts:** add `Source Date` (date): "Original date from the vault frontmatter or file name. Created can't be backdated." Add `Vault Path` (text): "Relative path of the source note in the Obsidian vault. Used to match and verify the migration; remove after sign-off."
- **Knowledge, Tags:** add the vault tags actually used (`product`, `sales`, `marketing`, `client`, `research`, `idea`, `tool`), lowercase.
- Log each change in the System Registry change log and on the registry pages.

### 4. Rules for the copy
1. **Bodies verbatim.** Strip the YAML frontmatter (it becomes properties). Keep headings, tables, code blocks and checklists.
2. **Frontmatter to properties:** title → Name (clean title, no date prefix); date → Source Date; ai → AI; status `ok` → active / published, `needs-attention` → Needs Attention ticked, `archived` → archived; tags → Tags (Knowledge only).
3. **Summary on every row:** the note's own `## Summary` section when it has one (first sentence), otherwise one line written from the note.
4. **Wikilinks in two passes.** Pass 1 copies `[[...]]` as plain text. Pass 2, after every page exists, replaces each wikilink with a Notion link to the new page, matched by Vault Path. Links to notes that weren't copied stay as text with "(vault only)".
5. **Several versions of one doc** (e.g. the three Social Outbound SOPs, two audit email sequences): copy all of them. The latest is active; older ones are archived and named with their date.
6. **Pilot 3 notes per destination, stop for JC's review,** then batches of 20 or fewer. Re-read each batch before the next (a failed write may still have saved).
7. **Log every note** on a Knowledge page "Migration log: vault to Operating System" (vault path | destination | new URL | notes). Unclear items get Needs Attention plus a line on the existing "Migration review list".
8. **Never edit or delete vault notes** during the migration.

### 4a. Inventory (2026-10-09)
The vault MCP's tree view is depth-limited and hid the client `SOPs/`, `call-prep/` and `client-facing-deliverables/` folders. A frontmatter search found them. Notes to copy, excluding `_fit/`, `business/SKILLS/`, vault system files, `PERMANENT-NOTE.md` placeholders and completed tasks:

| Area | Notes | Destination |
|---|---|---|
| Client projects: CAP 31, MAY 21, MOG 6, NWC 5, RFG 5, LFG 2, CCZ 1 | 71 | AI Drafts (~59); handoffs → Handoffs + Where things stand (5); learnings → Project pages (6); Howie's wants → Company page (1) |
| Internal product, Drive restructure, Quick SOP guide | 19 | Knowledge (handoff → Handoffs; overview → Product project page) |
| Sales-call prep, ghostops | 6 | AI Drafts |
| Marketing: writing 26, offers 8, instagram 3, materials 1, overview 1 | 39 | Posts (23), scripts, one-pager → AI Drafts; guides, offers, ideas → Knowledge; offers handoff → Handoffs; overview → Marketing project page |
| Sales (16), SOPs (5), ideas (13), research (3), About Blue Tusk (1) | 38 | Knowledge (sales overview → Sales project page; About → Blue Tusk company page) |
| Open tasks | 3 | Tasks |
| xx_needs-categorization (4) + _archived (5) | 9 | Sorted per note; _archived checked for duplicates |
| Personal | 18 | Private "Personal" page |
| **Total** | **~203** | |

Some notes have no frontmatter (e.g. `20260918_LendForGood_Client_Brief.md`, `20260818_Discovery_Brief_Ruthless_For_Good.md`, `call-prep/20260615_call-brief-maycomb-capital.md`): dates come from the file name. Non-standard statuses (`final`, `source-document`, `ready`, `complete`, `active`, `draft`) map to published / archived / active.

### 4a-bis. Change 2026-10-09 (JC): all business notes go to AI Drafts
Every business note (179) becomes an **AI Drafts** row on a project, replacing the Knowledge / Handoffs / Tasks / project-page destinations in Section 1. Client folders → their client project. Non-client notes: sales and SOPs → BTK-26070102 Sales Q4 (23); marketing, offers, posts, LinkedIn notes → BTK-26070101 Marketing Q4 (42); product and Drive restructure → BTK-26080701 Product (15); ideas, research, About Blue Tusk → BTK-26070199 Big Picture Q4 (17); Quick SOP guide and the open AI task → BTK-26070104 Systematize Q4 (2); sales-call briefs → the prospect's project where one exists. Type: sop, report, post, email, proposal or document. Status: ok / final / complete / ready / active / source-document → published; needs-attention → draft + Needs Attention; draft → draft; archived → archived; posts → draft + flagged unless marked published. The seven internal area projects were renamed to drop the quarter (BTK-26070101 Marketing, BTK-26070102 Sales, BTK-26070103 Admin, BTK-26070104 Systematize, BTK-26070105 Learning, BTK-26070106 Finance, BTK-26070199 Big Picture) and are evergreen homes for reusable material; sprints are tracked with a Sprint field on Tasks (2026-q4 set on the 30 open tasks). Import landed via a private staging page "Vault import (staging)"; personal notes under the private "Personal" page.

### 4b. Route for the bodies
The Notion connector only accepts page content inline, so a direct copy means Claude re-types every note (~200 notes, several over 800 lines). That is slow and is where verbatim copies go wrong. **Preferred route:** Notion's own Markdown import (Settings → Import → Text & Markdown) brings the bodies in faithfully, tables included, into a staging page. Claude then moves each imported page into its database (move-pages), strips the frontmatter text, and sets properties, Summary and Vault Path. Claude builds the zip of exactly the notes in scope (with folder access to the vault on JC's Mac), and JC runs the import once.

### 5. Order of work
1. Inventory pass: list every vault note with its destination per Section 1. Mark duplicates, exclusions and unclear items, and get the exact expected count per destination.
2. JC answers the decisions (Section 7) and approves the schema additions.
3. Apply schema additions; log them.
4. Knowledge (SOPs, guides, ideas, research, product and Drive docs).
5. AI Drafts (client project docs, posts, call briefs, ghostops).
6. Project and Company pages (handoffs → Where things stand, learnings, preferences, About Blue Tusk) + Handoffs rows.
7. Tasks from open vault tasks and outstanding questions.
8. Wikilink pass.
9. Verify: counts per destination vs inventory, 10 random spot checks per destination (body length and headings vs source), every flagged row listed.
10. Freeze the vault: add an "ARCHIVED: source of truth is Notion" banner to the vault README; stop creating vault notes. Update the context-handoff and vault-mcp skills to point at Notion (via skill proposals).

### 6. After the copy
- Handoff notes stop being vault files: the handoff skill writes Handoffs rows and "Where things stand" (architecture Section 4.6).
- **Backup next:** the git backup script is built once the copy is verified, then a restore drill. Only after that is the vault eligible for retirement.

### 7. Decisions for JC
1. **Personal notes** (Ellipsis logs, health and fitness, Italian study, misc, ~20 notes): a private top-level Notion page "Personal" outside the Operating System, plain pages, no databases? Or leave them in the vault archive?
2. **Completed vault tasks** (March to April, 3 files): skip? (Recommended: skip; they're done and in git history.)
3. **Notion AI's project calls that differ from what JC said:**
   - Capital Financing got the code **CAP** (the plan proposed CFN) and Stage **done**, but the vault has active work from Sept 2026 (CMO and AI engineer hire references). Is it still active?
   - Neighborworks (NWC-26061701) is **lost**; JC said it's a **proposal**.
   - LendForGood (LFG-26091801) is **lost**. Correct?
4. **Posts:** which LinkedIn posts in `marketing/writing/` were published? Default if unknown: draft, flagged.
5. **Schema additions** in Section 3: approve?

### Decided 2026-10-09 (JC)
1. Personal notes go to a private top-level Notion page "Personal", outside the Operating System, as plain pages.
2. Completed vault tasks are skipped.
3. Capital Financing stays CAP-26061201, Stage done. Neighborworks set to proposal (done in Notion). LendForGood stays lost.
4. Posts: default draft, flagged, unless the note says it was published.
5. Schema additions approved and applied 2026-10-09; logged in the System Registry change log.

## Next steps
- [x] JC: answer Section 7.
- [ ] Claude: inventory pass and expected counts.
- [x] Claude: schema additions.
- [ ] Claude: pilot.
