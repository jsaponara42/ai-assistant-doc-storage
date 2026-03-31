---
title: "Corporate Claws strategy — Blue Tusk positioning"
date: 2026-03-31
tags: [ai, strategy, tool]
ai: human
context: business
status: draft
related: []
summary: "Strategic note on 'Corporate Claws' (autonomous AI agents embedded in business operations). Covers how Blue Tusk should develop its own internal claws, how to deliver claw-compatible work to clients, and what this means for service design."
---

## Summary

AI agents that run autonomously inside businesses — referred to here as "Corporate Claws" — are an emerging operational layer. Blue Tusk needs both an internal claw strategy and a client delivery strategy that accounts for claw-ready implementations.

## Context

Prompted by a Shelly Palmer article: https://shellypalmer.com/2026/03/corporate-claws/

The core insight: companies are beginning to embed AI agents that operate continuously, not just respond to prompts. This has implications for how Blue Tusk delivers work and how clients should think about automation investments.

## Content

### Three areas to address

**1. Blue Tusk internal claws**
What AI agents should Blue Tusk run internally to operate the business? This includes lead gen, client delivery tracking, reporting, and task execution. The `tasks/ai-tasks/` folder in this vault is the first step toward this.

**2. Client deliverables that are claw-compatible**
Any automation system Blue Tusk builds for a PI firm client should be designed so a claw (AI agent) can operate it — not just a human. This means:
- Clear trigger/action structure (not buried in UI clicks)
- API-accessible or webhook-driven where possible
- Documented in plain language an agent can parse

**3. Command-line / agent-friendly implementations**
Where possible, implementations should be operable via CLI or structured API calls — not locked into GUIs. Zapier and Make.com both have API layers; prefer designs that expose those.

### Open questions

- Which Blue Tusk internal processes are highest-value for claw automation first?
- Should client SOPs include an "agent operation" section alongside the human operation guide?
- Is there a positioning angle here — "claw-ready automation" as a differentiator?

## Next steps

- Read the full Shelly Palmer article and extract relevant frameworks
- Draft a one-page internal Blue Tusk claw strategy
- Add a "claw compatibility" checklist to the client delivery SOP template
