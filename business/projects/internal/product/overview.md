---
title: "Product"
date: 2026-08-14
tags: [strategy, project, idea]
ai: claude
status: needs-attention
---

## Summary
Home for productization thinking — moving Blue Tusk from a pure time-for-money service business toward an owned, scalable product (client-facing "company brain" system and/or an operator-facing methodology/system product). Strategy is still being decided; nothing here is committed yet.

## Context
Emerged from an 2026-08-14 strategy conversation on radical differentiation, scalability, and target-buyer segments (see chat history — not yet transcribed into a permanent note per JC's instruction to hold off writing anything down until direction is decided). Directly related to prior thinking on scaling the internal vault/MCP system to a team: [[business/ideas/2026-07-10-scaling-vault-to-team]] — that note solves a different problem (many internal teammates collaborating on one shared knowledge base) than the product version needs to solve (many small, isolated client tenants, each likely with far fewer concurrent editors).

## Content
Open threads to resolve before committing to a direction:
- Two-track tension: near-term service cashflow vs. long-term product exit — how much of each engagement's effort goes toward reusable IP (template library, cross-client pattern dataset) vs. billable delivery.
- Target buyer / scalability question: financially sophisticated alt-asset & specialty-finance operators (proven traction) vs. PE portfolio companies sold through operating partners (higher potential ease-of-sale once relationship exists, but currently zero warm path in and unproven for Blue Tusk specifically).
- Architecture for a client-facing "company brain": likely simpler than the internal team-scaling problem — one MCP endpoint + API key per client tenant, rather than solving multi-person real-time collaboration on day one.
- Tool-integration vs. self-contained: leaning toward a self-contained knowledge/reasoning layer with narrow, mostly read-only integrations into 2-3 systems that hold a client's ground-truth data (mirrors what real engagements already do — Salesforce, SharePoint) rather than trying to replace existing tools.
- Editability: needs both AI (MCP) and direct human editing (plain markdown/git, or a lower-floor surface like Notion) converging on the same git-backed source of truth, so version control is inherited for free and no file is ever AI-only-editable.

## Next steps
- [ ] Decide the near-term/long-term resource split (Tier A vs. Tier B from the adversarial-analysis pass on the PE/scalability plan).
- [ ] Define the monetization checkpoint for the template library (e.g. 2 engagements showing measurably reduced bespoke build time) before investing further.
- [ ] Scope the human-editing surface for a non-technical client team (plain git/markdown vs. lightweight custom web editor vs. Notion-hybrid).
- [ ] Once direction is decided, write the actual product strategy doc here.
