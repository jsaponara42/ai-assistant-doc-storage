---
title: "Google Drive Taxonomy Test — Results (2026-10-07)"
date: 2026-10-07
tags: [ai, research, tool, project]
ai: claude
status: ok
---

# Google Drive Taxonomy Test — Results

## Summary
Hands-on test of Claude's Google connectors (Drive, Docs, Sheets, Slides) against a test folder in the Blue Tusk shared drive. **Google passed every capability the MOG architecture needs**, including the three that mattered most:
- **Editing an existing native Google Doc in place.**
- **Editing in suggestion mode** (tracked changes).
- **Doing what a comment asks and replying in its thread.**

Two limits need design rules:
- Full-text search covers the whole Drive and doesn't index new files right away.
- Agent actions appear under the connected person's name.

Outcome: **MOG decision D1 = Google.** The August capability note has been updated, since its "no edit-in-place" conclusion no longer holds once the editor connectors are on.

## Context
- **Why:** to decide D1 (Google vs SharePoint) in [[business/projects/client-projects/26092901_madrid-operations-group-AI-first-retainer/20261007_MOG_AI_Native_Stack_Architecture]]. It also carries out the "personal test" the August note asked for: [[business/projects/internal/product/20260816_ai-file-integration-capability-reality-check]].
- **Where:** [Taxonomy Test](https://drive.google.com/drive/folders/1m6MCZJuymSX3zCTEkO5Fs0HVhVusv1MM), in the Blue Tusk shared drive.
- **Test content:** two made-up clients (HRB Harbor Lending, OAK Oakfield Fund), laid out with MOG's proposed folder taxonomy. There's a `CONVENTIONS.md` at the root, a project code registry Sheet, client briefs, meeting notes, decision logs, drafts and delivered files. `OAK/04_delivered` and `06_Events` were left empty on purpose.
- **Connectors:** Drive at first. Docs, Sheets and Slides were added partway through for the editing tests.

## Content

### Results

| # | Test | Result | Notes |
|---|---|---|---|
| 1 | Find and write to a shared drive folder | ✅ Pass | Found by title search; `canAddChildren: true`. The August note had flagged shared drives as a known gap, and it didn't come up. |
| 2 | Create folders (nested 3 levels) | ✅ Pass | 21 folders. Drive connector, `application/vnd.google-apps.folder`. |
| 3 | Create native Google Docs | ✅ Pass | Upload HTML with conversion on; headings, lists, bold, italics and tables carry over. **Not .docx.** |
| 4 | Create native Google Sheets | ✅ Pass | Upload CSV with conversion on. Registry and hours tracker. |
| 5 | Keep a markdown file as `.md` | ✅ Pass | `text/markdown` with `disableConversionToGoogleType: true`. |
| 6 | Read `.md` back | ✅ Pass, noisy | The Drive reader escapes markdown symbols (`\#`, `\_`, `\*`). Readable, but `download_file_content` returns it clean. |
| 7 | List one folder's contents | ✅ Pass | `parentId = '<id>'` returned all five items of the client folder. |
| 8 | Full-text search | ⚠️ Limit | It searched **the whole Drive**, not the folder, and returned real Maycomb, RFG and LFG files. Test files created minutes earlier weren't indexed yet. |
| 9 | Edit an existing doc in place: add a sentence and delete a placeholder | ✅ Pass | Docs connector. Targeted insert and delete, locked to the revision just read. Headings kept their styles, nothing else changed, same link. |
| 10 | Edit in suggestion mode | ✅ Pass, quirk | `writeMode: SUGGEST` worked and was confirmed as a suggested insertion. **Quirk:** a new paragraph right after a heading inherits the heading style, so it took a second suggestion (style back to normal text). The reviewer sees two suggestions and must accept both, or use "Accept all." |
| 11 | Read a comment, do what it asks, reply "Done" in the thread | ✅ Pass | Comment read through Drive `read_file_content` with `includeComments`. Edit made with `replaceAllText`. Reply added with `addCommentReply` in the same thread, which was left open. |
| 12 | Reply author | ⚠️ Limit | The reply posted as **John-Carlos Saponara**. Connectors act as the person who connected them. |

### Design rules from the findings (applied to MOG)
1. **Never rely on search for client isolation (#8).** Agents work from folder IDs and listings scoped by `parentId`, not full-text search across the Drive. This reinforces isolated Projects per client and the conventions rule "stay in one client's folder per task." Full-text search is only for discovery, and only by people.
2. **Expect indexing lag (#8).** Agent flows shouldn't search for files they just created; they should keep the IDs returned at creation.
3. **Label agent actions (#12).** Agent comment replies and doc notes start with a prefix such as "🤖 Claude:", because they otherwise appear under Martina's or Ashley's name.
4. **Comments are an instruction source, so control who can issue them (#11).** Agents only act on comments from approved people (Martina, Ashley, Alexis, JC), and confirm before any action outside the doc itself (sending, sharing, deleting). In a shared or client-facing doc, comments from anyone else are treated as information, never as instructions.
5. **Read comments through Drive, not the Docs reader (#11).** The Docs reader's comment option didn't return them; the Drive reader did.
6. **Expect paired suggestions (#10).** Tell Martina and Ashley that agent suggestions for new paragraphs show up as text plus formatting, and to use "Accept all" or accept both.
7. **Draft-and-confirm can now live inside the doc.** Suggestion mode means a Review Queue item can point at a doc that already holds the tracked changes. Martina reviews in Google Docs itself rather than comparing a separate draft.

### Not tested yet
- Native Claude Projects per client: loading `CONVENTIONS.md` and a brief, then checking that the agent stays out of other clients' folders.
- Full-text search a day later, to see whether the test files got indexed.
- Sheets and Slides editing.
- Editing an Office file (.docx/.xlsx) stored in Drive. Editing has only been confirmed on native Google files.
- Behavior with a non-owner account (e.g. Ashley's access level).

## Next steps
- [ ] Add rules 3–5 to MOG's real `CONVENTIONS` doc when it's built (Phase 0).
- [ ] Run the Claude Project isolation test in the Taxonomy Test folder.
- [ ] Re-run full-text search tomorrow for indexing.
- [ ] Feed results into the Layer 1.5 / Layer 3 positioning in [[business/projects/internal/product/20260814_information-taxonomy-offering-stack]].


---

## Token cost: Google Docs vs markdown (logged 2026-10-07)

**Bottom line:** reading a Google Doc's text is cheap. Editing a Google Doc is expensive, because every index-based edit needs a full structure read first. Repeatedly updating Google Docs would make agent token spend unaffordable. **Workflows must be designed around this, not discovered later.**

### What we observed (same ~1-page SOP doc, from this session's tool results)

| Operation | Approx. size returned | Rough tokens | Relative to markdown |
|---|---|---|---|
| Markdown file, read directly | ~1,000 chars | ~250–300 | 1x |
| Google Doc, text read (Drive `read_file_content`) | ~1,050 chars | ~300 | ~1x |
| Google Doc, structure read (Docs `read_doc`, required for index-based edits) | ~35,000+ chars of JSON | ~9,000–10,000 | **~30–40x** |
| One-sentence suggestion edit, end to end (read → write → verify read) | 2 structure reads + write | ~20,000 | **~100–200x** vs a markdown find-and-replace |
| Full-document text replacement (`replaceAllText`, no read needed) | write only | ~100–300 | ~1x |
| Creating a doc (HTML upload) | ~1.5–2x the markdown | small | ~1.5–2x |

**Why the structure read is so big:** every paragraph carries about 1.5K characters of style data (mostly empty border, padding and shading settings), and every read includes a block defining all the heading styles. Long docs and tables make it worse. These are estimates from today's tool results, not a controlled benchmark.

### Cost rules (these feed the MOG architecture)
1. **Markdown first.** Agents draft, iterate and keep notes in markdown in the client's `_ai/` folder. Google Docs are for publishing, not for working.
2. **Publish once, then edit sparingly.** Create the formatted Google Doc when content is settled (cheap). After that, only small, targeted changes.
3. **Prefer edits that need no read.**
   - **Find-and-replace** of a unique phrase needs no structure read. It's the default edit method, and it's what the comment test used.
   - **Appending at the end of a document** (`endOfSegmentLocation`) needs no index and no read. Agent-maintained logs therefore add new entries **at the bottom**, not the top. This changes the "newest at top" convention used in the test drive.
4. **One structure read per doc per task, at most.** If an index-based edit can't be avoided, batch every change into one read and one write.
5. **Verify with the text read, not the structure read.** Re-reading the structure just to confirm an edit doubles the cost. A text read (~1x) is enough to confirm content.
6. **Suggestion mode only for the final human review.** Never iterate in suggestion mode. Iterate in markdown, then make one batch of suggestions.
7. **Put high-frequency logs in the cheapest format.** Decision logs, hours and commitment lists are updated constantly, so they belong in markdown (agent-side), a Sheet (adding rows is cheap) or Notion, not in a formatted Google Doc.
8. **When a whole document needs rewriting, consider republishing.** Many targeted edits to one doc can cost more than publishing a new version. The tradeoff is that a new file means a new link, so only do this at version milestones, and archive the old version.

### Still to test
- Actual token use with the google-workspace skill's helper script condensing a saved structure read, where code can run.
- Cost on a long document with tables, to put a realistic number on a client brief or SOP.
- Whether appending with `endOfSegmentLocation` keeps formatting clean in a decision log.


---

## Markdown in Drive / `_ai/` storage — UNRESOLVED (logged 2026-10-07)

> **Status: open. JC isn't happy with the current workaround and wants to come back to this, because the cost adds up over time.** The `_ai/` folder (agent notes, context handoff, rough drafts) needs a storage format that is cheap to edit in place, and nothing tested so far fully works.

### Tests run (in `01_Clients/HRB_Harbor-Lending/_ai/`)

| Test | Result |
|---|---|
| Create a real `.md` file in Drive | ✅ Works (`text/markdown`, conversion off) |
| Edit the `.md` with the Docs editor connector | ❌ Refused: "The document must not be an Office file." The editor only works on native Google Docs. |
| Edit the `.md` with Drive `update_file` | ❌ No content field; it can only rename or move. |
| Overwrite by creating a file with the same name in the same folder | ❌ Created a **duplicate** with a new ID. Both duplicates are still in `_ai/` (not trashed). |
| Plain Google Doc holding markdown-style text: find-and-replace + append at end | ✅ Both worked with no structure read; same ID and link; checked with a cheap text read (~300 tokens) |
| Structure read on that plain doc | ⚠️ **Still bloated:** ~240 characters of text → ~30K+ characters of JSON (~8K tokens, over 100x). Worse proportionally than the formatted SOP (30–40x). |

### Key findings
- **Drive connectors can't edit a real markdown file in place.** You can create and read one, never update it. Every "update" means a new file, a new ID, and duplicates or trash clutter.
- **Markdown syntax inside a Google Doc doesn't reduce cost.** Google stores every line, blank lines included, as a paragraph with a full block of style data. Importing plain text made it worse, because every font and text setting was written out explicitly. **Structure-read cost scales with the number of paragraphs, not with how the doc looks.**
- **Writes are lean on any format.** The cost is in the structure read needed for positional edits (insert mid-list, delete a line, restyle).
- **Cheap editing works only on two paths:** find-and-replace of a unique phrase, and append at the end. Both are limited, and agents will need positional edits sooner or later, at ~8K+ tokens per read for even a tiny doc.

### Options on the table

| Option | Edit in place? | Cost | Tradeoffs |
|---|---|---|---|
| **A. Real `.md` in Drive, replaced on every change** | No: new file each time, old one trashed | Cheap per write | ID and link change every time, duplicates if a trash step fails, trash clutter. Only workable for rarely changed files. |
| **B. Plain Google Doc with markdown-style text** *(current workaround)* | Yes, but only with find-and-replace and append | Cheap on those paths; **~8K+ tokens per structure read** for anything positional | Shows raw `#` and `-` to people. Text reads come back escaped. Cost creeps up with doc length and with every positional edit. **JC doesn't love this.** |
| **C. Notion pages for AI working notes** | Yes, through the Notion connector | Expected to be cheap: content comes back as markdown-like text. **Not tested yet.** | Splits AI notes from the client's Drive folder, but Notion is already MOG's records layer. Needs the per-client isolation and connector-switching questions answered. |
| **D. Drive desktop sync + Claude Code / Cowork editing local `.md` files** | Yes: real files, real in-place edits | Cheapest (plain text edits) | Needs the desktop app and a local machine. **Doesn't work from claude.ai chat or cloud scheduled tasks.** Sync conflicts possible. |

Other ideas, not yet explored:
- **E. A custom MCP server for Drive markdown,** like JC's vault server. It would read, find-and-replace and write `.md` files through the Drive API, which can replace a file's content without changing its ID. The connector exposed today doesn't offer that. This is the same pattern as JC's vault, pointed at Drive. More build and maintenance, but it may be the cleanest long-term fix and could be part of the Blue Tusk offering.
- **F. A GitHub repo per client (or per firm) for AI notes,** synced the same way JC's vault is. Real markdown and cheap edits, but a new tool for non-technical clients.

### What to check when revisiting
1. Test **Option C** (Notion): read and edit cost, and whether a native Claude Project can be kept to one client's Notion pages.
2. Look at **Option E**: whether the Drive API's update-content endpoint can be wrapped in a small MCP server, and how hard that would be to host for clients.
3. Put a number on the ongoing cost of Option B for one realistic workflow (e.g. a daily handoff update plus weekly drafts) to see whether "it adds up" is $5/month or $50/month.
4. Decide whether the `_ai/` content needs to live in Drive at all, or whether "AI memory lives somewhere else, finished work lives in Drive" is the cleaner split.

**Until this is resolved:** use Option B with cheap edits only (find-and-replace, append at the end, text reads). Keep AI docs short, with no blank lines between sections, and avoid positional edits.


---

## File operations: move, rename, trash (logged 2026-10-07)

| Test | Result | Notes |
|---|---|---|
| Move a file between folders in the shared drive (`update_file` with a new folder) | ❌ "The caller does not have permission" | Tried moving `_ai/` → `03_drafts/`. |
| Rename the same file (`update_file` title) | ✅ Pass | Same ID. The duplicate was renamed `xx_context-handoff_DUPLICATE.md`. |
| JC's access on that file | Manager ("organizer") | The highest shared drive role, so moving should be allowed. |
| Trash a file in the shared drive (`trash_file`) | ✅ Pass | Trashed the `_DUPLICATE.md`. Folder listing confirmed it's gone. Restorable from shared drive trash. |

**Findings:**
- **Moving is the only blocked operation.** Create, rename and trash all work in the shared drive. Trashing there also needs Manager-level access, so the connector can act on shared drive files, and the move call specifically fails. **Likely cause, not confirmed:** the connector doesn't send the API flag for shared drive support on moves (parent changes).
- **Not tested yet:** moving a file in **My Drive**, which would show whether moves fail everywhere or only in shared drives. It wasn't run because it means putting a test folder in JC's personal My Drive.

**Design implications (observations, no decisions made):**
- Agents can't reorganize folders in the shared drive. That fits the existing conventions rule that agents don't restructure folders.
- Moving a draft into a delivered folder (`03_drafts` → `04_delivered`) can't be done by an agent today. The alternatives are to do it by hand, or for the agent to publish a new file into the delivered folder (cheap) and trash the draft.
- **For D9 / the UNRESOLVED `_ai/` storage question:** Option A ("real `.md` in Drive, replaced on each change") is now **technically possible**, since both creating a new file and trashing the old one work. The open tradeoffs are unchanged: a new ID and link on every change, duplicates if a trash step fails, and trash clutter. **Recorded as new evidence only. D9 is still not decided.**

**Updated file-operations scorecard (shared drive):**

| Operation | Result |
|---|---|
| Create file or folder | ✅ |
| Rename | ✅ |
| Move between folders | ❌ (permission error despite Manager access) |
| Trash | ✅ |
| Edit content in place | ✅ native Google Docs only; ❌ `.md` |


---

## Notion editing test (logged 2026-10-08)

**Why:** to test whether Notion is a cheap place for agents to draft and keep living context (it became the design: Notion = drafts, Drive = finals). Full design: [[business/projects/internal/product/20261008_ai-native-operating-architecture]].

**Setup:** a scratch database "SCRATCH - AI Drafts Test" (private, in JC's Notion workspace; delete when testing is done). Properties mirror vault frontmatter, plus Summary, Client, Project ID, Type, Status, Needs Attention, Final Link and Drive Folder. Three draft rows: a short handoff, a ~1-page SOP and a ~3,600-character plan.

| Operation | What came back | Rough tokens |
|---|---|---|
| Create database + 3 pages | Properties only | small |
| Catch-up query (3 rows: name, client, status, flag, summary, created; last 7 days) | ~1,000 chars | ~250 |
| "Needs attention" query | ~400 chars | ~100 |
| Read a full page (3,600 chars of text) | ~5,000 chars | ~1,250 |
| Find-and-replace edit | page ID only | tiny |
| Append at end | page ID only | tiny |
| Property update (Status, Final Link, Drive Folder) | page ID only | tiny |

**Results:**
- **Both content edits landed correctly with no read beforehand.** Last Edited updated automatically.
- **Summary works as the catch-up layer:** agents can scan recent work from query results alone.
- **Compared with Google Docs:** the same one-sentence edit cost ~20K tokens with verification in Google, and ~100 (or ~1,350 with a re-read) in Notion. That's **roughly 15–200x cheaper.**
- **Quirks:**
  - Checkboxes come back as `__YES__` / `__NO__`.
  - Created time is automatic and can't be backdated, so rows created together share a timestamp.
  - **SQL queries are unlimited only on Business / Enterprise with Notion AI.** Other plans share a workspace limit; use filter-based queries or saved views there.

**This resolves the UNRESOLVED `_ai/` storage question above for drafts and context:** they live in Notion, not Drive. The markdown limits in Drive still apply to anything that has to be stored there.
