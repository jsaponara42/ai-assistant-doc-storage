---
title: Workflow Waste Audit — Notion Report Skill
date: 2026-03-30
tags:
  - project
  - ai
  - client
  - tool
ai: claude
context: business
status: ok
related:
  - overview.md
  - 2026-03-30-audit-call-flow.md
summary: Claude skill specification for generating a Notion-ready markdown audit report from a PI firm discovery call transcript. Includes the full report structure, Mermaid flowchart syntax, quick win scoring logic, and cost estimation formulas.
---

# Audit Report — Notion Markdown Generator Skill

This skill converts a PI firm discovery call transcript or structured call notes into a complete, Notion-ready audit report in markdown format.

## How to use

Drop a call transcript or call notes into a Claude conversation and prompt:
> "Generate the audit report from this transcript"

Claude will read the skill, follow the structure, and produce the full Notion-ready markdown in one pass inside a fenced code block ready to paste.

## Report sections (in order)

1. Title Block — firm name and date
2. Executive Summary — dollar figure, top priority, dashboard upsell signal
3. Firm Snapshot — leads, CRM, tools, team
4. Process Map — Mermaid flowchart color-coded by automation status
5. Quick Win Diagnostic — scored card for each of the four quick wins
6. Open Pain — their exact language from the call
7. Metrics & Visibility Assessment — dashboard upsell signal
8. Next Steps — prioritized action plan + guarantee

## Quick win areas scored

- **Referral Machine** — post-settlement follow-up, reviews, referrals
- **Case Status Automation** — proactive milestone updates to clients
- **No-Show Eliminator** — intake appointment reminders and reschedule sequences
- **New Client Onboarding** — retainer, forms, document collection automation

## Status scoring

- Automated — system handles it without staff involvement
- Partial — something exists but manual steps remain
- Manual/None — a person does it every time or it doesn't happen
- Unknown — topic not discussed on the call

## Mermaid flowchart color codes

| Status | Color |
|---|---|
| Automated | #27AE60 (green) |
| Partial | #F39C12 (amber) |
| Manual/Gap | #C0392B (red) |
| Unknown | #8A95A3 (gray) |
| Fixed nodes (New Lead, Post-Close) | #1B2A4A (navy) |

## Important Notion syntax note

In Notion Mermaid blocks, use `\n` for line breaks inside node labels — **not** `<br>`. Example:
```
B["Intake Appt\n⚠️ PARTIAL"]
```

## Cost estimation defaults (when data is missing from transcript)

| Quick Win | Default Annual Cost Range |
|---|---|
| Referral Machine | $5,000–$15,000/yr |
| Case Status Automation | $5,000–$25,000/yr |
| No-Show Eliminator | $4,000–$10,000/yr |
| New Client Onboarding | $10,000–$25,000/yr |

Show estimation math inline: *(assumed: X hrs/week × $35/hr × 50 weeks = $Y/yr)*

## Guarantee language (include in Next Steps)

> If the first automation we build doesn't produce a measurable result within 30 days of going live, we work free until it does.

## Skill install location

The packaged `.skill` file for this is saved as `audit-report-notion-skill.skill` in outputs. Install via Claude settings → Skills.

# References
[[business/sales/2026-04-03-free-workflow-audit-free-offer-creation-agp]]
[[business/sales/2026-03-30-audit-call-flow|2026-03-30-audit-call-flow]]