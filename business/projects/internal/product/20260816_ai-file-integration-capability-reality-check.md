---
title: "AI File Integration — What's Actually Possible Today (Reality Check for Layer 3)"
date: 2026-08-16
tags: [ai, project, strategy, research]
ai: claude
status: ok
---

# AI File Integration — What's Actually Possible Today (Reality Check for Layer 3)

## Summary
> **⚠️ Updated 2026-10-07: the Google Drive conclusion below is out of date.** With Claude's Google Docs/Sheets/Slides editor connectors turned on, Claude **can** edit existing native Google Docs in place, including in **suggestion mode** (tracked changes). It can also read a comment, do what it asks and reply in the thread. Confirmed hands-on: [[business/projects/internal/product/20261007_google-drive-taxonomy-test-results]]. See "Update 2026-10-07" at the end. The original August text is kept below as a record.

*(Original, August 2026)* The "AI working-partner layer" (Layer 3) implicitly pitches AI working directly inside a client's existing files. That capability doesn't exist yet on the major platforms — today's real ceiling is **read + create-new-file only, no in-place editing** of anything already in Google Drive, and **read-only, full stop** on SharePoint via ChatGPT (Claude gained a narrow, admin-gated write path in July 2026). This note grounds Layer 3 in what's actually deliverable right now, so the offering isn't sold on a capability that doesn't exist yet.

## Context
Follows [[business/projects/internal/product/20260814_information-taxonomy-offering-stack]]. That doc already builds in a "propose-don't-act" boundary for Layer 3 (draft only, human confirms) — this note doesn't change that decision, it confirms *why* it's the right one and sharpens the sales framing around it. JC's business runs on Google Drive, which is also the platform to test against first.

## Content

### What the platforms actually allow today (August 2026)

**Google Drive — Claude and ChatGPT alike:**
- Read: yes — search, open, and pull content from existing files.
- Write: **create-new only.** Claude can generate a new document and save it into a Drive folder, but it lands as an Office file (.docx/.xlsx/.pptx), not a native Google Doc/Sheet.
- Edit-in-place: **not possible.** No connector can rewrite a paragraph, fix a formatting error, or update a cell in a file that already exists. "Fix the typo in paragraph three" comes back as corrected text to paste yourself — not an edit.
- This isn't a guess — it's confirmed directly by the tool set on JC's own connected Google Drive: the available actions are share, trash, and move/rename (metadata only). There's no read-content or write-content tool exposed at all in this setup.

**SharePoint / OneDrive:**
- ChatGPT: read-only, full stop — no create, no edit, no upload, even in the newer "Work" agent mode.
- Claude: read-only by default, but as of **July 7, 2026** gained write tools (create and update files) via the Microsoft 365 connector — off by default, and an admin has to turn it on. Early and narrow, but it's the first crack in "edit-in-place" appearing anywhere on a major platform.

**Net read:** the "AI works inside your files" benefit doesn't exist as a shipped, default capability for a Google Drive-based client today. For a SharePoint/M365-based client, it's just barely starting to exist, gated behind an admin decision most companies haven't made yet.

### Why this matters for Layer 3, specifically
The current offering doc already has the right instinct — "propose-don't-act," draft-only, ride the client's own platform AI over time rather than hosting it. This finding says: **don't treat that as a temporary compromise, treat it as the honest and only sellable version of Layer 3 right now.** Concretely:
- Don't market "AI edits your files for you." That's not true today, on any platform, for the vast majority of prospects (Google Drive shops especially).
- Do market "AI drafts inside your structure, you confirm." This is real, deliverable today, and happens to be exactly what the meeting-transcript flagship use case already requires — transcript in, drafted task/SOP update out, human approves before anything touches a live system. That flow needs zero in-place-edit capability to work.
- The SharePoint write-tools development is worth watching, not building on. It's admin-gated and one vendor, one connector, two months old — not a foundation to promise a client.

### Personal test — before this gets sold
JC's business runs on Google Drive, so that's the right first test environment, and it should happen before Layer 3 (or even the taxonomy migration mechanics) get pitched as deliverable.

Suggested test, kept small and concrete:
1. Point Claude's Google Drive connector at a real (or deliberately messy) folder and confirm what it can actually find — flag if Shared Drive content comes back empty, which has been reported elsewhere as a known gap.
2. Run the flagship Layer 3 flow end to end: feed it something transcript-like, have it draft a new task/SOP-update document, save it as a new file into the right folder per the taxonomy — and check how much friction is left for the human "confirm" step in practice (is it a clean save-and-review, or awkward copy/paste).
3. Try a taxonomy-migration-style task: ask it to propose a reorganization of a messy folder as a set of new, correctly-placed files, rather than actually moving anything — since move/reorganize-in-place isn't available either.
4. Note anywhere the deliverable quietly depends on a paid third-party bridge (there are a few — e.g. tools that give Claude a real edit-in-place workflow by working on a copy in their own workspace) versus what native connectors alone can do. Decide only after seeing it firsthand whether that's worth building into delivery or worth avoiding as an extra vendor dependency.

The goal isn't a full pilot — it's confirming, hands-on, that the draft-and-confirm version of Layer 3 is actually smooth enough to deliver before it's in a sales conversation.

## Next steps
- [x] Run the personal test above against JC's own Google Drive before Layer 3 is pitched to anyone. **Done 2026-10-07.** See the update below.
- [ ] Rewrite any Layer 3 marketing language. **Revised direction:** in-place editing and suggestion mode now work on Google. The pitch can be "AI drafts inside your documents as tracked suggestions, and you accept them," which keeps draft-and-confirm while dropping the separate-file friction.
- [ ] Recheck this note in ~2–3 months. This is a fast-moving space.
- [ ] If a client is SharePoint/M365-based rather than Google Drive, re-verify capability separately. Not re-tested in October.


---

## Update 2026-10-07: Google re-tested hands-on

Full results: [[business/projects/internal/product/20261007_google-drive-taxonomy-test-results]]

**What changed since August.** The August finding (Google Drive is "create-new only, no edit-in-place," new files land as .docx) reflected **the Drive connector alone**. Claude now has separate **Google Docs, Sheets and Slides editor connectors**. With those on, the ceiling is much higher:

| Capability | August (Drive connector only) | October (Drive + editor connectors) |
|---|---|---|
| Read existing files | Yes | Yes |
| Create new files | Yes, as Office files | **Yes, as native Google Docs and Sheets** (HTML or CSV converted on upload); `.md` kept as markdown |
| Edit an existing file in place | No | **Yes:** targeted inserts, deletes and replacements in a native Google Doc, locked to the version just read |
| Suggestion mode (tracked changes) | No | **Yes.** One quirk: a new paragraph after a heading shows up as two suggestions (text plus formatting) |
| Read comments | n/a | **Yes**, through the Drive reader (the Docs reader's comment option returned nothing) |
| Reply in a comment thread | n/a | **Yes**, in the same thread |
| Shared drives | Reported gap | **Worked** (read, write, create) |

**What still holds.**
- **Draft-and-confirm is still the right design.** The reason is no longer only a technical limit; it comes from client gates (e.g. Martina's non-negotiables). Suggestion mode makes it smoother: the draft lives inside the real document as tracked changes, not in a separate file.
- **SharePoint/M365 wasn't re-tested.** The August SharePoint findings stand until checked.
- **Editing Office files (.docx/.xlsx) stored in Drive wasn't tested.** Editing is only confirmed on native Google files.

**New limits found (they need design rules, not workarounds).**
- **Full-text search covers the whole Drive**, not one folder, and doesn't index new files right away. Agents should work from folder IDs. Client isolation can't rely on search.
- **Agent actions appear under the connected person's name.** Label agent replies with a prefix.
- **Comments are an instruction source.** Agents should act only on comments from approved people, and confirm anything that reaches outside the doc.

**What this means for the offering stack.**
- **Layer 3** can now credibly promise "AI works inside your Google Docs as tracked suggestions you accept," which is stronger than "AI drafts new files."
- The **meeting-transcript flagship** gets easier: close-out updates can land as suggestions in the client's living docs.
- **Layer 1 (taxonomy) gets more important, not less.** The search finding shows agents need structure, scoped folders and conventions to stay in the right place. Better connectors don't remove that need.
