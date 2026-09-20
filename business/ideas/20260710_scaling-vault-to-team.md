---
title: "Scaling the vault + MCP system to a team"
date: 2026-07-10
tags: [idea, strategy, ai, tool]
ai: claude
status: needs-attention
---

## Summary
Brainstorm on options for scaling the current solo Obsidian + filesystem-MCP + git setup to a full team, all with Claude access. Covers hosting/access, merge-conflict prevention, direct human markdown editing, and teaching conventions to people (not just agents).

## Context
The current system (OneDrive-synced Obsidian vault, git for versioning, a `filesystem` MCP server pointed at the vault root, `CONVENTIONS.md`/skill files teaching Claude the rules) works well solo. JC is exploring what breaks first at team scale and what the options are for each failure point.

## Content

### 1. Hosting + shared MCP access
- **Rejected: N local MCPs.** Each teammate running their own local `filesystem` MCP against their own clone means N different configs (paths, setup steps, staleness) to maintain and debug. Explicitly not worth it — config drift scales with headcount.
- **One remote MCP server (the actual reason for a VPS).** Host a single `filesystem` MCP instance on a VPS, backed by its own clone of the GitHub repo — it pulls before reads, commits + pushes after writes. Every teammate's Claude (desktop/CLI, and later a Slack bot) points at the *same* remote endpoint with the *same* config. One thing to set up and maintain instead of N.
- **Git-as-source-of-truth**: a private GitHub/GitLab repo is the real store underneath; the VPS-hosted MCP is just the one canonical client that reads/writes through it. Gets PR review, history, rollback for free.
- This is separate from how humans edit markdown directly (see option 5) — that path never touches the MCP at all.
- If a Slack bot gets added later (option 6), it's just another client of this same server — the always-on requirement is already satisfied by centralizing for config consistency, so Slack doesn't add a new infra requirement on top.

### 2. Avoiding merge conflicts
Raw git isn't built for real-time concurrent editing — conflicts happen when two people touch the same lines between commits.
- **Ownership by convention**: one clear owner per folder/project; others leave comments/tasks instead of editing directly. Cheap, relies on discipline.
- **Frequent small commits + pull-before-edit** as a hard rule to keep conflicts rare and small.
- **Obsidian Sync (paid) or self-hosted LiveSync (CouchDB plugin, free)**: both do real conflict-aware merging instead of folder-sync's "last write wins."
- **Split by contention**: move genuinely real-time-collaborative material off git entirely (see option 3), keep git/markdown for lower-contention material (SOPs, reference, AI-generated docs).

### 3. Direct human editing in markdown
Same underlying problem, human-facing side.
- Obsidian Sync or self-hosted LiveSync fixes the merge behavior directly.
- Bigger architectural fork: keep Obsidian+git for AI-and-JC material, move fast-moving team-collab material to something built for concurrency — Notion is already connected via MCP, so a hybrid (Notion as human collab surface, periodic sync into the vault for AI context) is a real option worth scoping, not just a tangent.

### 4. Teaching conventions
Different problem for humans vs. agents.
- **Agents**: already solved via compact `CONVENTIONS.md` reference cards the skill reads before acting (same pattern just extended for client projects).
- **Humans**: Obsidian Templater plugin — auto-inserts correct frontmatter/structure on "new note," removes reliance on memory.
- **At team scale**: pre-commit git hook or CI check validating frontmatter schema, naming pattern, and folder placement — catches drift at commit time instead of relying on someone having read the doc once.

### 5. Team direct-edit workflow (independent of the MCP)
- Converges on the workflow JC already uses solo: each teammate clones the GitHub repo, opens it in Obsidian, uses the **Obsidian Git plugin** to pull before editing and push after.
- This never touches the filesystem MCP — it's a second, independent access path into the same GitHub repo, running alongside the one centralized MCP from option 1. Two paths, one source of truth.
- Everyone (human and AI) converges on GitHub as the real source of truth, so option 2's conflict discipline (small commits, pull-before-edit) is what actually prevents collisions between the two paths.

### 6. Slack as the interface layer, scoped per channel
Idea: run team access through Slack, where each channel maps to its own folder (plus a few global reference folders), rather than exposing the whole vault to everyone.
- **Cost/search efficiency — real win.** Scoping the MCP's visible root to a channel's folder means much smaller `directory_tree` calls and less to search across per request. Directly addresses the AI-cost concern.
- **Simultaneous-edit awareness — partial win.** Solves it for *Slack-mediated* edits: if two people are both asking Claude-in-Slack to touch the same file, channel activity makes that visible. It does **not** cover someone editing the file directly in Obsidian (option 5's workflow) at the same time someone else asks Slack-Claude to edit it — that's a different access path into the same repo. Git discipline from option 2 is still the real backstop, not a replacement.
- **Needs a mapping file**: channel → allowed folder(s), same pattern as `CONVENTIONS.md`/`CLIENT-PROJECTS.md` — a small reference doc (e.g. `SLACK-CHANNEL-MAP.md`) the agent reads before acting, rather than hardcoded logic.
- **Open question**: how cross-project work gets handled if scoping is strict (e.g. "compare workflow maps across all clients") — may need a broader-access admin/analytics channel as an escape hatch.
- Also naturally gives permissioning for free (Slack channel membership = folder access) and a built-in audit trail (thread history) alongside git history.

## Next steps
- Decide how many people realistically need write access before over-building infra.
- Prototype self-hosted LiveSync vs. Obsidian Sync cost/effort tradeoff.
- Scope what a Notion-hybrid layer would actually look like if team collab material moves there.
- If pre-commit validation is worth it, define the checks (frontmatter fields present, naming regex, folder whitelist) before building the hook.
- Stand up the VPS + GitHub source-of-truth and test the pull/push discipline with just JC + one other person before wider rollout.
- Draft a channel → folder mapping doc and test Slack-scoped search cost savings on one active client channel.
