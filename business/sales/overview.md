---
title: Blue Tusk Go-To-Market — Project Overview
date: 2026-03-30
tags:
  - project
  - strategy
  - client
ai: claude
context: business
status: ok
related:
  - 2026-03-30-audit-call-flow.md
  - 2026-03-30-pre-call-screening-survey.md
  - 2026-03-30-audit-report-skill.md
  - 2026-03-30-blog-instructionbot-prompt.md
  - 2026-03-30-blog-writing-prompt.md
summary: Complete go-to-market system for Blue Tusk's Free Workflow Waste Audit offer targeting PI law firms. Covers cold email, Calendly event, discovery call flow, audit report delivery, and blog content infrastructure.
---

## Summary

This project contains all operational and marketing assets for Blue Tusk's primary go-to-market motion: a Free Workflow Waste Audit that converts to a $2,500–$5,000/month retainer. Assets span the full funnel from cold email outreach through audit delivery and blog content.

## Context

Blue Tusk targets personal injury law firms. The sales motion is:
1. Cold email → book a 30-minute audit call
2. Discovery call → score four quick win areas
3. 72-hour report delivery via Notion
4. Debrief call → close on monthly retainer

The four quick wins that the audit surfaces and the retainer implements:
- **Referral Machine** — post-settlement follow-up automation
- **Case Status Automation** — proactive client milestone updates
- **No-Show Eliminator** — intake appointment reminders
- **New Client Onboarding** — retainer, forms, and document collection automation

## Content

### Assets in this project

| File | Description |
|---|---|
| `2026-03-30-audit-call-flow.md` | 30-minute discovery call flow, phases, questions, and notes template |
| `2026-03-30-pre-call-screening-survey.md` | Calendly intake survey questions, disqualification logic, confirmation copy |
| `2026-03-30-audit-report-skill.md` | Claude skill for generating Notion-ready audit reports from transcripts |
| `2026-03-30-blog-instructionbot-prompt.md` | InstructionBot prompt — generates article topic/instructions |
| `2026-03-30-blog-writing-prompt.md` | Blog writing prompt — produces full 800–900 word SEO articles |

### Calendly event
- **Blue Tusk Workflow Audit** — https://calendly.com/bluetuskllc/blue-tusk-workflow-audit
- 30 minutes, Google Meet, navy brand color
- Intake survey to be added manually in Calendly UI (API does not support custom question updates)

### Retainer pricing
- $2,500–$5,000/month depending on scope and firm size
- Guarantee: measurable result within 30 days of go-live or Blue Tusk works free until it does

## Next steps

- Add intake survey questions to Calendly event manually (see pre-call screening survey file)
- Complete first live audit call and generate first real report using the skill
- Launch cold email campaign targeting PI firms via Instantly.ai
- Begin blog content production using the two-prompt system
