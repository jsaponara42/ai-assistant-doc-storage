# Vault conventions (agent reference)

> Full rationale and examples: [[CONVENTIONS-FULL]]

## Placement
- Inbox / unsure → `xx_needs-categorization/`
- Personal → `personal/` | Work/client → `business/`
- Within context: named project → `projects/project-name/` | standalone ref → `research/` | speculative → `ideas/`
- Task for AI → `tasks/ai-tasks/` | Task for JC → `tasks/jc-tasks/`

## File naming
- Notes: `YYYY-MM-DD-kebab-description.md` (3–5 words)
- Tasks: `{priority}-YYYY-MM-DD-kebab-description.md`
- Exception: `overview.md` (no date prefix, one per project subfolder)

## Frontmatter (required on every file)
```yaml
---
title: ""
date: YYYY-MM-DD
tags: []
ai: claude | chatgpt | gemini | human
context: personal | business
status: draft | active | archived
related: []
summary: ""
---
```
- `summary` is the most important field — 1–2 sentences, self-contained
- `context` must match top-level folder
- Add `updated: YYYY-MM-DD` when revising

## Tags
`ai` `project` `research` `idea` `tool` `strategy` `client` `task`

## Task workflow
1. Create task file in `tasks/ai-tasks/` or `tasks/jc-tasks/`
2. Add entry to `TASK-LOG.md` under `## Active`
3. On complete: set `status: archived`, move file to `completed/`, check off entry in `TASK-LOG.md` and move line to `## Completed`

## Note body structure
`## Summary` → `## Context` → `## Content` → `## Next steps` (optional)
