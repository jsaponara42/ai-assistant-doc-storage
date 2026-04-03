---
title: Create tasks folder structure in vault
date: 2026-03-31
due-date: 2026-04-03
priority: 1
tags:
  - pkm
  - obsidian
  - setup
ai: claude
context: personal
status: complete
related: []
summary: Task to create a top-level tasks/ folder in the vault with ai-tasks/ and jc-tasks/ subfolders. Each task file should have due-date and priority (1–3) in frontmatter, with priority and date in the filename.
---

## Summary

Create a `tasks/` folder at the vault root with two subfolders: `ai-tasks/` and `jc-tasks/`. This enables pointing an AI agent directly at its own task queue and keeping JC's manual tasks separate.

## Context

Came up during vault cleanup. The intent is to eventually point an AI agent at `ai-tasks/` and have it execute autonomously. Also allows task creation with consistent metadata.

## Content

### Folder structure

```
tasks/
├── ai-tasks/    ← tasks for AI agents to execute
└── jc-tasks/    ← tasks for JC to complete manually
```

### File naming convention

`{priority}-{YYYY-MM-DD}-{short-description}.md`

Example: `1-2026-04-01-update-index.md`

### Required frontmatter for all task files

```yaml
---
title: ""
date: YYYY-MM-DD
due-date: YYYY-MM-DD
priority: 1 | 2 | 3
tags: []
ai: claude | human
context: personal | business
status: draft | active | archived
summary: ""
---
```

Priority scale: **1 = highest**, 3 = lowest.

## Next steps

- [x] Create `tasks/`, `ai-tasks/`, `jc-tasks/` folders
- [ ] Update `CONVENTIONS.md` to document the tasks folder
- [ ] Update `INDEX.md` to include tasks folder
