---
name: vault-mcp
title: Vault MCP — Obsidian Vault Connector Conventions
date: 2026-07-23
tags:
  - ai
  - obsidian
  - pkm
  - tool
  - setup
ai: claude
status: ok
---
---
Use this skill whenever working with JC's Obsidian vault via the custom 'vault' MCP connector. Triggers on: saving notes, reading notes, searching the vault, managing tasks, categorizing inbox files, updating TASK-LOG.md, moving, copying, or deleting vault files, or any request involving vault file operations. Always use this skill before touching any vault tool — it contains the routing rules, conventions, and correct tool usage patterns for this connector.
---
# Vault MCP Skill

## This vault has a dedicated MCP server

The connector is the custom **`vault`** MCP server (`vault-mcp-server.mjs`), scoped to the vault root (`ai-assistant-doc-storage`, running locally on JC's Mac). It exposes purpose-built tools — no generic filesystem tools are used for vault work:

`get_vault_structure`, `pull_vault`, `read_note`, `save_note`, `patch_note`, `append_to_note`, `delete_note`, `move_note`, `copy_note`, `search_notes`.

Every write tool (`save_note`, `patch_note`, `append_to_note`, `delete_note`, `move_note`, `copy_note`) commits locally to git automatically. JC still pushes/pulls to GitHub manually via Obsidian Git (`pull_vault` handles the pull side if he wants Claude to trigger it).

## Session start

1. Call `get_vault_structure` to see the current tree (markdown files only, scoped automatically — no need to pass a path).
2. Call `read_note` on `CONVENTIONS.md` — compact reference card (~220 words).
3. Proceed. Do NOT read `CONVENTIONS-FULL.md` unless explicitly asked.
4. If JC wants remote changes synced first, call `pull_vault` before step 1.

---

## Tool reference (vault MCP)

| Tool | Use for | Notes |
|---|---|---|
| `get_vault_structure` | Full markdown-only tree before placing a new file | No args; skips `.` and `node_modules` dirs; depth-limited internally |
| `pull_vault` | Pull latest from GitHub | Run manually at session start only if JC wants a resync |
| `read_note` | Full file content | `filename` is a relative vault path |
| `save_note` | Create a new note, or fully overwrite an existing one | Commits locally. Prefer `patch_note` for edits to existing files |
| `patch_note` | Targeted search-and-replace (multiple edits in one call) | Each edit needs exact `oldText`; set `all: true` to replace every occurrence |
| `append_to_note` | Append to end of file, or before an anchor string | No read required — pass `before_anchor` to insert before a known heading/marker |
| `delete_note` | Delete a note | Commits the deletion; recoverable from git history |
| `move_note` | Rename/relocate via `git mv` | Preserves history; creates parent dirs as needed |
| `copy_note` | Clone a note to a new path | Errors if destination exists — use `save_note` to overwrite instead |
| `search_notes` | Regex search across all `.md` files | Returns file, line number, matched line (capped at 120 chars). Optional `path_filter` to scope to a subfolder, optional `flags` (default `"i"`) |

### Key rules

- **Prefer `patch_note` over `save_note`** for any edit to an existing file — `save_note` fully overwrites and risks losing unrelated content.
- **`append_to_note` needs no prior read** — unlike before, TASK-LOG entries and similar appends are a single call.
- **`search_notes` replaces manual reconstruction** — don't fall back to `get_vault_structure` + reading every candidate file; use the regex search first and only read matches that need full context.
- **`delete_note` actually deletes and commits** — no more "tell JC to delete it manually." It's still recoverable via git history if needed.
- **Cross-tool path note:** the `vault` MCP only resolves paths inside the vault root. It cannot read or write Claude's own sandbox paths. If a file was built in the sandbox first, re-read its content and pass it explicitly into `save_note` for the vault — there's no direct copy between the two filesystems.
- All local commits are automatic on writes. Pushing to the GitHub remote remains JC's manual step via Obsidian Git.

---

## Placement routing

```
Inbox / unsure          → xx_needs-categorization/
Personal                → personal/
Work / client           → business/
  Named project         → {context}/projects/project-name/
  Standalone reference  → {context}/research/
  Speculative idea      → {context}/ideas/
Task for AI agent       → tasks/ai-tasks/
Task for JC             → tasks/jc-tasks/
```

---

## File naming

- **Notes:** `YYYY-MM-DD-kebab-description.md` (3–5 words, lowercase)
- **Tasks:** `{priority}-YYYY-MM-DD-kebab-description.md`
- **Exception:** `overview.md` — no date prefix, one per project subfolder

---

## Frontmatter (required on every file)

```yaml
---
title: ""
date: YYYY-MM-DD
tags: []
ai: claude | human
status: needs-attention | ok | archived
---
```

Tasks also include `due-date: YYYY-MM-DD` — omit the field entirely if no date specified.

- `ai` = which assistant wrote it (`human` if JC wrote it)
- `status` — `needs-attention` = requires review/action, `ok` = current, `archived` = done/superseded

### Valid tags
`ai` `obsidian` `pkm` `github` `project` `research` `idea` `tool` `setup` `mobile` `pwa` `strategy` `client` `task`

---

## Task workflow

### Creating a task
1. `save_note` to create the new file in `tasks/ai-tasks/` or `tasks/jc-tasks/`.
2. `append_to_note` on `TASK-LOG.md` with `before_anchor` set to the `## Completed` heading (or whatever anchor the file actually uses — confirm with `read_note` if unsure).

Entry format:
```
- [ ] YYYY-MM-DD | [[filename-without-extension]] | short description
```

### Completing a task
1. `patch_note` on the task file to set `status: archived` in the frontmatter.
2. `move_note` the file into the `completed/` subfolder.
3. `patch_note` on `TASK-LOG.md`: check the box (`- [ ]` → `- [x]`) and update the wikilink target to `completed/filename`. One call with both edits if they're on the same line, otherwise two edits in the same `patch_note` call.

---

## Note body structure

```
## Summary     ← required, 1–3 sentences
## Context     ← background, why it came up
## Content     ← main body
## Next steps  ← optional
```

---

## Common patterns

### Add a TASK-LOG entry
```
append_to_note(
  filename: "tasks/jc-tasks/TASK-LOG.md",
  content: "\n- [ ] 2026-07-21 | P1 | [[1-2026-07-21-my-task]] | Do the thing",
  before_anchor: "\n---\n\n## Completed"
)
```

### Patch a frontmatter field
```
patch_note(
  filename: "path/to/note.md",
  edits: [{ oldText: "status: draft", newText: "status: active" }]
)
```

### Find all draft notes in business/
```
search_notes(pattern: "status: draft", path_filter: "business")
```

### Find overdue tasks
```
search_notes(pattern: "due-date: 2026-0[1-6]", path_filter: "tasks")
// then read_note on any file worth checking in full
```

### Categorize an inbox file
1. `read_note` on the inbox file.
2. Determine placement from the routing table above.
3. `save_note` to the correct destination with full frontmatter + headings.
4. `delete_note` on the original inbox file.

### Copying a file as a template
```
copy_note(source: "path/to/template.md", destination: "path/to/new-file.md")
// then patch_note to adjust the copied content as needed
```

### Moving content from Claude's own sandbox into the vault
The `vault` connector cannot see Claude's sandbox paths. If a file was already built there, read its content first, then pass that content directly into `save_note` at the vault destination — there's no cross-filesystem move or copy.