# Vault conventions

This file is the first thing any AI agent should read before interacting with this vault. It describes the folder structure, file naming rules, frontmatter schema, and tagging conventions.

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
├── INDEX.md                    ← auto-maintained map of all notes — read second
├── README.md                   ← human-facing repo description
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

- Use `personal/` for anything related to private life, personal goals, hobbies, or general knowledge
- Use `business/` for anything work, client, or professionally oriented
- Within each context, choose the type folder:
  - `projects/` — tied to a specific named effort with more than one note. Create a kebab-case subfolder, e.g. `business/projects/ai-assistant-pwa/`
  - `research/` — standalone reference not tied to a specific project
  - `ideas/` — low-friction capture, no minimum quality bar. Ideas that mature into projects get moved or linked via `related` field
- `overview.md` files (one per project subfolder) do not need a date prefix

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

`INDEX.md` is auto-maintained by the vault MCP server on every commit. It contains a table of all notes with their title, date, context, tags, and summary. **Do not edit INDEX.md manually.**

Agents should read `INDEX.md` after `CONVENTIONS.md` to get a full map of the vault before deciding which notes to read in depth.

---

## Agent instructions

If you are an AI agent reading this file:

1. Read `CONVENTIONS.md` (this file) first
2. Read `INDEX.md` to get an overview of what exists
3. Use the `summary` frontmatter field to decide which notes are worth reading in full
4. When saving a new note, infer placement from the content:
   - Personal topic → `personal/`
   - Work/professional topic → `business/`
   - Within context: tied to a named project → `projects/project-name/`, standalone reference → `research/`, speculative → `ideas/`
5. Always populate the `summary` frontmatter field — this is the most valuable metadata for future retrieval
6. Set `ai` field to the assistant that generated the note
7. Never edit `INDEX.md` directly — it is auto-generated on every commit by the MCP server
