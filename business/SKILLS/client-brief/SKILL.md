---
name: client-brief
title: "Client Brief Generator — Transcript to Structured Brief"
date: 2026-06-15
tags: [tool, ai, client, project]
ai: claude
status: ok
description: "Generates a structured client project brief from a recorded meeting transcript. Use this skill whenever the user uploads or pastes a call/meeting transcript and wants it turned into a client brief, project brief, client dossier, or onboarding document — triggers on phrases like 'create a brief from this transcript', 'turn this call into a brief', 'build the client dossier', 'update the brief with this new meeting', or any request to produce or evolve a structured client document from meeting notes. Also use when the user uploads a second transcript for an existing client and wants the prior brief extended. Always use this skill when a transcript is provided and a client brief is the goal — even if the user does not say the word 'skill'."
---

# Client Brief Generator

Converts a recorded meeting transcript into a structured client project brief, and grows that brief over time as more meetings are added.

## What this produces

A single markdown brief covering the client's organization, business profile, goals, key people, technology, a register of diagnosed problems, and an action plan. The analytical depth mirrors a senior consultant's dossier, but the section labels are plainspoken (no branded framework jargon).

## Before you start — three things to determine

1. **Is this a new brief or an update to an existing one?**
   - If the user mentions there is an existing brief **in the vault**, locate and read it first (use the vault tools / `vault-mcp` skill). Build on it.
   - If the user says they will upload the brief, or attaches one, read that and build on it.
   - Otherwise, treat this as a brand-new brief.

2. **Read the structure reference** before writing anything:
   - `references/brief-structure.md` — the full section-by-section template, what goes in each section, and the plainspoken labels to use.

3. **Locate the transcript(s)** the user uploaded (check `/mnt/user-data/uploads/`) and read them in full.

## Workflow

1. Determine new-vs-update and read the existing brief if there is one (see above).
2. Read `references/brief-structure.md`.
3. Read the transcript(s) in full.
4. Extract everything the transcript supports into the brief structure. Write in the same dense, declarative style as the template (short factual sentences; names, numbers, roles stated plainly).
5. **Mark every gap.** Wherever the transcript doesn't supply something the structure calls for, insert a visible placeholder: `> ⚠️ NEEDS INPUT: <specific question>`. Do not silently invent facts. Reasonable inferences are allowed but must be labeled `*(inferred)*`.
6. Output the full brief as a markdown file (see Output below).
7. **Then ask the user the gap questions.** After presenting the file, collect every `NEEDS INPUT` marker from the brief into a single numbered list in your chat message, so the user can answer all of them in one pass. Number them and group related ones together (e.g. all missing contact details for one person on one line). After they answer, update the brief and re-present it.

## Updating an existing brief

When a prior brief exists, you are extending it, not replacing it:
- Preserve everything still accurate. Don't drop sections the new transcript didn't touch.
- Add new people, problems, and decisions surfaced in the new meeting.
- Where the new meeting changes a prior fact (a decision made, a person exited, a vendor chosen), update it and note what changed in a short `## Changelog` entry at the top with the meeting date.
- Re-mark any gaps that are still open.

## Output

- Save the brief to `/mnt/user-data/outputs/` as a markdown file.
- Filename format: `YYYYMMDD_ClientName_Brief.md` using the meeting date (or today's date if unknown).
- Present the file to the user, then list the open `NEEDS INPUT` questions.

## Quality checks before delivering

- Every section from the structure reference is present (use "Not discussed" if a section has no data rather than omitting it).
- Every gap is marked with a `NEEDS INPUT` callout and collected into the closing question list.
- Inferences are labeled; nothing is silently fabricated.
- People are listed with role, and any stated contact details / tenure / working style.
- Problems each have the four parts: the problem, the current thinking sustaining it, the reframe, and the approach.
- On an update, a changelog entry records what this meeting changed.
