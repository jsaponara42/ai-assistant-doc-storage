---
title: "SOP Formatting Guide"
date: 2026-04-30
last-updated: 2026-04-30
tags: [strategy, ai]
ai: claude
status: ok
---

# SOP Formatting Guide

This file defines how SOPs are written and structured in `business/SOPs/`. It is the reference for any agent or human creating or updating an SOP in this folder.

---

## File Naming

```
YYYY-MM-DD-SOP-[Descriptive-Name].md
```

The name should be unambiguous about what process the SOP governs. Use sentence-case words separated by hyphens. Avoid abbreviations unless universally understood in context.

**Good:** `2026-04-30-SOP-Cold-Outreach-PI-Firms.md`
**Bad:** `2026-04-30-outreach.md`, `2026-04-30-SOP-v2.md`

When a process is substantially revised, update `last-updated` in the frontmatter and revise the file in place. Do not create a new file unless the old process is being archived entirely.

---

## Frontmatter

Every SOP requires this frontmatter — no more, no less:

```yaml
---
title: "SOP — [What This Process Is For]"
date: YYYY-MM-DD
last-updated: YYYY-MM-DD
tags: [strategy, sales] (or whatever applies)
ai: claude | human
status: ok | needs-attention | archived
---
```

`date` is the creation date — never change it.
`last-updated` is bumped every time the body of the SOP changes.
`status: archived` is set when a process is fully retired and replaced.

Do not add a `supersedes` field to frontmatter. Lineage belongs in the body of the document — see below.

---

## Required Sections

Every SOP must contain these sections in this order:

### 1. Summary
1–3 sentences. What process does this SOP govern, and why does it exist in its current form? If this SOP replaced a previous approach, say so briefly here.

### 2. Previous Methods (Superseded)
List all prior approaches this SOP replaces, with wikilinks to the source files. This is where lineage lives — not in frontmatter.

Format:
```
- Brief description of prior method: [[path/to/file]]
- Another prior method: [[path/to/file]]
```

If this is the first version of a process with no prior methods, write: `This is the first documented version of this process.`

### 3. Why This Method Replaced the Previous One
What evidence, analysis, or decision led to the current approach? Keep it factual and brief. Link to any supporting research or adversarial analysis documents.

If this is the first version, omit this section.

### 4. Current Process
The step-by-step process. Numbered steps. Each step should be actionable — a person or agent reading it should know exactly what to do and in what order.

Sub-steps, quality checks, and conditional branches (if X then Y) are fine and encouraged where the process has them.

### 5. What to Track
What data or outcomes should be recorded as this process runs? Be specific — field names, what a "success" looks like, what triggers a review.

### 6. What Is Not In Scope
Explicit list of related things this SOP does not cover, and where to find them if documented elsewhere. This prevents scope creep and clarifies boundaries.

### 7. Next Review
When and under what conditions should this SOP be revisited? Tie it to data or outcomes, not just a calendar date.

---

## Wikilink Conventions

Use Obsidian-style wikilinks for all cross-references to other vault files:

```
[[path/to/file-without-extension]]
```

Always use the full path from the vault root. Do not use relative paths.

Link to source files, research documents, skill files, and prior SOPs wherever they are referenced in the body. Never link to files that don't exist yet — use plain text and a note to create the file instead.

---

## Tone and Style

- Write in imperative second person for process steps: "Send the email." "Run the skill." Not "The agent should send the email."
- Write in plain declarative prose for context sections (Summary, Why This Replaced, etc.)
- No bullet points for process steps — use numbered lists
- Bullet points are acceptable in non-sequential sections (What Is Not In Scope, Previous Methods)
- No headers beyond H2 and H3 — keep the document flat
- Do not pad. If a section is genuinely not applicable, say so in one line and move on.

---

## When to Create a New SOP vs. Update an Existing One

**Update in place** when:
- A step changes but the overall process is the same
- A tool or link changes
- Wording needs to be clearer

**Create a new SOP** only when:
- The process is being fundamentally replaced by a different approach
- The old process needs to be preserved for reference (set old file to `status: archived`)

In practice, most changes are updates. A new file should feel like a meaningful decision, not a default.
