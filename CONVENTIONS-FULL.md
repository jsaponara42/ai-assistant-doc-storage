# Vault conventions (full reference)

> This is the human-readable version with rationale and examples.
> Agents use [[CONVENTIONS]] — the compact reference card.

---

## Purpose

This vault is a personal knowledge base for John-Carlos. Its primary uses are:

1. **Building context before AI conversations** — agents read relevant notes before a session to understand background, history, and current state of projects
2. **Generating new documents from notes** — agents synthesize across notes to produce reports, summaries, proposals, and reference docs

---

## Folder structure

```
vault/
├── CONVENTIONS.md              ← compact agent reference card (read this)
├── CONVENTIONS-FULL.md         ← this file — full rationale and examples
├── INDEX.md                    ← lightweight routing map
├── README.md                   ← human-facing repo description
├── xx_needs-categorization/    ← quick-capture inbox
├── tasks/
│   ├── ai-tasks/
│   │   ├── TASK-LOG.md         ← active + completed checklist
│   │   ├── completed/          ← completed task files
│   │   └── *.md
│   └── jc-tasks/
│       ├── TASK-LOG.md
│       ├── completed/
│       └── *.md
├── personal/
│   ├── projects/project-name/
│   │   ├── overview.md
│   │   └── *.md
│   ├── research/
│   └── ideas/
└── business/
    ├── projects/project-name/
    │   ├── overview.md
    │   └── *.md
    ├── research/
    └── ideas/
```

### Folder placement rules

- Use `xx_needs-categorization/` as the default inbox for fast capture. Notes here can be rough or unstructured.
- During cleanup, move inbox notes into `personal/` or `business/` when intent is clear.
- `personal/` — private life, personal goals, hobbies, general knowledge
- `business/` — work, client, or professional topics
- Within each context:
  - `projects/` — tied to a named effort with more than one note. Use a kebab-case subfolder.
  - `research/` — standalone reference not tied to a specific project
  - `ideas/` — low-friction capture, no quality bar. Mature into projects when ready.
- `overview.md` files (one per project subfolder) do not use a date prefix
- Do not create assistant-named subfolders. Use the `ai` frontmatter field instead.

---

## File naming

Format: `YYYY-MM-DD-short-description.md`

- Date = creation date (not last edited)
- Kebab-case, all lowercase, 3–5 words
- No spaces or special characters
- Exception: `overview.md` — no date prefix
- Exception: task files — `{priority}-YYYY-MM-DD-description.md`

---

## Frontmatter schema

```yaml
---
title: "Human-readable title"
date: YYYY-MM-DD
tags: [tag1, tag2]
ai: claude | chatgpt | gemini | human
context: personal | business
status: draft | active | archived
related: []
summary: "1–2 sentences. Self-contained description of what this note contains."
---
```

When revising, add: `updated: YYYY-MM-DD`

### Field notes

- `summary` — most important field. An agent reading only frontmatter should understand the note without opening it.
- `context` — must match the top-level folder the file lives in.
- `ai` — use `human` for manually written notes.
- `related` — list of relative vault paths. Empty array if none.
- `status` — `draft` = new/incomplete, `active` = current reference, `archived` = superseded or completed task.

---

## Tag vocabulary

Add new tags here when genuinely needed. Use existing tags before creating new ones.

| Tag | Use for |
|---|---|
| `ai` | AI tools, models, workflows, prompting |
| `obsidian` | Obsidian setup, plugins, configuration |
| `pkm` | Personal knowledge management |
| `github` | Git workflows, repositories |
| `project` | Notes tied to a named project |
| `research` | Reference material |
| `idea` | Brainstorms, speculative thinking |
| `tool` | A specific tool or technology |
| `setup` | Configuration and setup |
| `mobile` | Mobile-related notes |
| `pwa` | Progressive web apps |
| `strategy` | Business strategy, planning |
| `client` | Client-specific notes |
| `task` | Task files in tasks/ |

---

## Tasks folder

### Task file naming
`{priority}-YYYY-MM-DD-short-description.md`
Priority: **1 = highest**, 2 = normal, 3 = low

### TASK-LOG.md
One per subfolder. Running checklist of all tasks — active and completed.

Entry format:
```
- [ ] YYYY-MM-DD | P{n} | [[filename-without-extension]] | short description
```

On completion, check the box, update the date to completion date, move the line to `## Completed`, and update the wikilink to `completed/filename`.

### Completing a task
1. Set `status: archived` in the task file's frontmatter
2. Move the task file into `completed/`
3. Check off the entry in `TASK-LOG.md` and move it to `## Completed`

### Task frontmatter
```yaml
---
title: ""
date: YYYY-MM-DD
due-date: YYYY-MM-DD
priority: 1 | 2 | 3
tags: [task]
ai: claude | human
context: personal | business
status: draft | active | archived
related: []
summary: ""
---
```

---

## Note body structure

```markdown
## Summary
1–3 sentences. What this note is and why it matters.

## Context
Background, why this came up, relevant history.

## Content
Main body.

## Next steps
(Optional) Actions, open questions, follow-ups.
```

---

## Wikilinks

```markdown
[[2026-03-30-note-name]]
[[personal/projects/project-name/overview|Display label]]
```

---

## INDEX.md

Lightweight routing map only. Include:
- Top-level folders
- Active projects (links to `overview.md`)
- Recent notes (last 7–14 days, capped)

Do not turn it into a full vault dump.
