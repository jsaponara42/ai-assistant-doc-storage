# Vault conventions

This file is the first thing any AI agent should read before interacting with this vault. It describes the folder structure, quick-capture workflow, file naming rules, frontmatter schema, and tagging conventions.

---

## Purpose

This vault is a personal knowledge base for John-Carlos. Its primary uses are:

1. **Building context before AI conversations** — agents read relevant notes before a session to understand background, history, and current state of projects
2. **Generating new documents from notes** — agents synthesize across notes to produce reports, summaries, proposals, and reference docs

---

## Folder structure

```
vault/
├── CONVENTIONS.md              ← this file — read first
├── INDEX.md                    ← lightweight routing map
├── README.md                   ← human-facing repo description
├── xx_needs-categorization/    ← quick-capture inbox for rough personal notes
│   └── *.md
├── tasks/                      ← task queue for humans and AI agents
│   ├── ai-tasks/               ← tasks for AI agents to execute autonomously
│   │   ├── COMPLETED-TASKS.md  ← running checklist log of completed tasks
│   │   ├── archived/           ← completed task files moved here when done
│   │   └── *.md                ← individual active task files
│   └── jc-tasks/               ← tasks for JC to complete manually
│       ├── COMPLETED-TASKS.md  ← running checklist log of completed tasks
│       ├── archived/           ← completed task files moved here when done
│       └── *.md                ← individual active task files
├── personal/
│   ├── projects/               ← personal projects, one subfolder per project
│   │   └── project-name/
│   │       ├── overview.md     ← project summary, goals, current status
│   │       └── *.md
│   ├── research/               ← personal reference material, learning notes
│   │   └── *.md
│   └── ideas/                  ← personal brainstorms, speculative thinking
│       └── *.md
└── business/
    ├── projects/               ← work/client projects, one subfolder per project
    │   └── project-name/
    │       ├── overview.md
    │       └── *.md
    ├── research/               ← professional reference, technology evaluations
    │   └── *.md
    └── ideas/                  ← business brainstorms, strategic thinking
        └── *.md
```

### Folder placement rules

- Use `xx_needs-categorization/` as the default inbox for fast personal capture. Notes here can be rough, partial, or unstructured.
- During cleanup, move inbox notes into `personal/` or `business/` when the intent is clear.
- Use `personal/` for anything related to private life, personal goals, hobbies, or general knowledge
- Use `business/` for anything work, client, or professionally oriented
- Within each context, choose the type folder:
  - `projects/` — tied to a specific named effort with more than one note. Create a kebab-case subfolder, e.g. `business/projects/ai-assistant-pwa/`
  - `research/` — standalone reference not tied to a specific project
  - `ideas/` — low-friction capture, no minimum quality bar. Ideas that mature into projects get moved or linked via `related` field
- `overview.md` files (one per project subfolder) do not need a date prefix
- Do not create assistant-specific subfolders (for example `claude/`). Track assistant origin in the `ai` frontmatter field.

---

## Tasks folder

The `tasks/` folder is the action queue for the vault. It has two subfolders:

- `tasks/ai-tasks/` — tasks an AI agent should execute. An agent can be pointed at this folder to run autonomously.
- `tasks/jc-tasks/` — tasks JC needs to complete manually.

### Task file naming

Format: `{priority}-{YYYY-MM-DD}-{short-description}.md`

Examples:
- `1-2026-04-01-update-index.md`
- `2-2026-04-03-draft-claw-strategy.md`

Priority scale: **1 = highest**, 2 = normal, 3 = low.

### COMPLETED-TASKS.md

Each subfolder contains a single `COMPLETED-TASKS.md` — a running checklist log of every task that has been finished.

**Entry format:**
```
- [x] YYYY-MM-DD — [[archived/filename-without-extension|Task title]]
```

- The date is the **completion date**
- The wikilink points into the `archived/` subfolder where the task file was moved
- Entries are added **most-recent-first**
- Do not delete entries or the `archived/` files they reference — this is the permanent record

**Example:**
```markdown
## Completed

- [x] 2026-03-31 — [[archived/1-2026-03-31-create-tasks-folder-structure|Create tasks folder structure]]
- [x] 2026-04-02 — [[archived/2-2026-03-30-update-index|Update INDEX.md with new folders]]
```

### Completing a task — step by step

1. Update the task file's `status` frontmatter to `archived`
2. Move the task file into `archived/` within the same subfolder
3. Add a line to `COMPLETED-TASKS.md` (most-recent-first, under `## Completed`)

### Task frontmatter schema

```yaml
---
title: "Human-readable task title"
date: YYYY-MM-DD
due-date: YYYY-MM-DD
priority: 1 | 2 | 3
tags: [tag1, tag2]
ai: claude | human
context: personal | business
status: draft | active | archived
related: []
summary: "One sentence describing what this task requires."
---
```

Both `due-date` and `priority` are required for all task files.

---

## File naming

Format: `YYYY-MM-DD-short-description.md`

Examples:
- `2026-03-30-obsidian-git-setup.md`
- `2026-03-30-pwa-capture-tool-idea.md`

Rules:
- Always prefix with the date the note was **created** (not last edited)
- Use kebab-case, all lowercase
- Keep the description short — 3 to 5 words
- No spaces, no special characters
- Exception: `overview.md` files inside project subfolders do not use a date prefix
- Exception: task files use `{priority}-{date}-{description}.md` format (see Tasks folder above)

---

## Frontmatter schema

Every markdown file must begin with a YAML frontmatter block:

```yaml
---
title: "Human-readable title of the note"
date: YYYY-MM-DD
tags: [tag1, tag2]
ai: claude | chatgpt | gemini | human
context: personal | business
status: draft | active | archived
related: []
summary: "One or two sentence description of what this note contains."
---
```

### Field rules

| Field | Required | Description |
|---|---|---|
| `title` | yes | Sentence case, descriptive. Used by INDEX.md and agents without reading the body |
| `date` | yes | Creation date, ISO 8601 |
| `tags` | yes | See tag vocabulary below. Use existing tags before creating new ones |
| `ai` | yes | Which assistant generated the note. Use `human` for manually written notes |
| `context` | yes | Must match the top-level folder (`personal` or `business`) |
| `status` | yes | `draft` for new/incomplete, `active` for current reference, `archived` for superseded |
| `related` | no | List of relative paths to related notes. Empty array if none |
| `summary` | yes | **Most important field for agents.** 1-2 sentences capturing the core content. An agent reading only frontmatter should understand what the note contains |

When revising an existing note, add an `updated` field:

```yaml
updated: YYYY-MM-DD
```

---

## Tag vocabulary

Use only tags from this list. Add new tags to this list when genuinely needed.

| Tag | Use for |
|---|---|
| `ai` | AI tools, models, workflows, prompting |
| `obsidian` | Obsidian setup, plugins, configuration |
| `pkm` | Personal knowledge management concepts |
| `github` | GitHub, git workflows, repositories |
| `project` | Notes that belong to or describe a project |
| `research` | Research and reference material |
| `idea` | Brainstorms and speculative thinking |
| `tool` | A specific tool or technology being evaluated |
| `setup` | Configuration and setup notes |
| `mobile` | Mobile-related notes and tools |
| `pwa` | Progressive web apps |
| `strategy` | Business strategy, planning |
| `client` | Client-specific notes |
| `task` | Task files in the tasks/ folder |

---

## Note body structure

Follow this structure where applicable:

```markdown
## Summary

1-3 sentences. What this note is about and why it matters.

## Context

Background, why this topic came up, relevant history.

## Content

The main body of the note.

## Next steps

(Optional) Actions, open questions, follow-ups.
```

The `## Summary` section is the most important — agents can extract just this section cheaply without reading the full note.

---

## Wikilinks

When a note references another note in this vault, use Obsidian-style wikilinks:

```markdown
See also: [[2026-03-30-obsidian-git-setup]]
```

Or with a display label:
```markdown
See also: [[personal/projects/ai-pwa/overview|AI PWA project overview]]
```

---

## INDEX.md

`INDEX.md` is intentionally lightweight. It should help agents route quickly, not list every note.

Use this structure:
- Current top-level folders
- Active projects (with links to `overview.md`)
- Recently added notes (last 7-14 days, capped)

Do not turn `INDEX.md` into a full vault dump. Full-note discovery should come from folder scans and frontmatter filtering.

---

## Agent instructions

If you are an AI agent reading this file:

1. Read `CONVENTIONS.md` (this file) first
2. Check `INDEX.md` for fast routing only
3. Use folder scans and the `summary` frontmatter field to decide which notes are worth reading in full
4. When saving a new note, infer placement from the content:
   - Fast personal capture with unclear destination → `xx_needs-categorization/`
   - Personal topic → `personal/`
   - Work/professional topic → `business/`
   - Within context: tied to a named project → `projects/project-name/`, standalone reference → `research/`, speculative → `ideas/`
   - Actionable task → `tasks/ai-tasks/` or `tasks/jc-tasks/` depending on who should execute
5. Always populate the `summary` frontmatter field — this is the most valuable metadata for future retrieval
6. Set `ai` field to the assistant that generated the note
7. Never create assistant-named folders; the `ai` field is the source-of-truth
8. When completing a task: set `status: archived` in frontmatter, move the file to `archived/`, and add a line to `COMPLETED-TASKS.md`
