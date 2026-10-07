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
