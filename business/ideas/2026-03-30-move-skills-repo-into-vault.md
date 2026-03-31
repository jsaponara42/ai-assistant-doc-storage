---
title: "Idea: Move skills repo into vault"
date: 2026-03-30
tags: [ai, pkm, tool, idea]
ai: human
context: business
status: draft
related: []
summary: "Idea to consolidate the external LLM skills repo (llm-agent-skills on GitHub) into this vault for simplicity and single-source-of-truth access."
---

## Summary

It may be worthwhile to move the external `llm-agent-skills` GitHub repo into this vault so everything lives in one place.

## Context

Currently, Claude skills and agent skill specs live in a separate GitHub repo. Having them here would simplify context loading for AI agents and reduce friction when updating or referencing skills.

## Content

Consider merging or symlinking the skills repo into `business/projects/` or a dedicated top-level `skills/` folder. Evaluate tradeoffs:

- **Pro:** Single vault, simpler agent context loading, no switching repos
- **Con:** Skills repo may be more broadly reusable outside of this personal vault; mixing personal notes with reusable tooling may create noise

## Next steps

- Decide on folder placement (e.g., `business/projects/llm-agent-skills/` vs. top-level `skills/`)
- Evaluate whether skills should stay public on GitHub or move private into this vault
