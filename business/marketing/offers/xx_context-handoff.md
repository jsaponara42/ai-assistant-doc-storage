---
title: "Close Q4 Strong Entry Offer — Context Handoff"
date: 2026-09-23
tags: [handoff, project]
ai: claude
status: ok
---

# Close Q4 Strong Entry Offer — Context Handoff

> Fresh-start note. Read this first. Only pull in the linked files below if the current task needs that level of detail.

## Where things stand
Blue Tusk's 3-stage entry-offer funnel is fully designed: free automated magnets (Stage 1) → $1,500 / $497 / homework-gated Teardown (Stage 2) → $10K Roadmap (Stage 3). Now building Stage 1 **linearly**, one piece at a time. The shared intake form is designed and built in Jotform, and waiting on JC's manual editor pass. Next build piece: the Manual-Process Cost Estimate logic.

## Last worked on (2026-09-23)
- Designed the intake form backward from engine outputs: about 10 screens, taps for numbers, two voice-dictation prompts, "last time it happened" framing, frequency × duration instead of "hours wasted," softened qualification (revenue range + intent question, no budget ask)
- Decided the **backend reads the prospect's website after submission** (the form itself never pulls live). Website URL is now required; site signals are supporting evidence only and never create hour or dollar figures
- Built the form in Jotform, including a device-specific dictation tutorial and hidden `hook`/UTM fields, then ran a fix pass for pieces the first build dropped
- Patched the main offer note (Step 3 and the cost-estimate mechanic) to match

## Open / next
- **JC, in the Jotform editor:** switch to Card Form layout (the connector can't add page breaks), check field order, apply brand styling, turn on save-and-continue, test conditional logic, run a phone test using dictation
- **Next build:** Manual-Process Cost Estimate logic (role/industry hourly defaults, range math, owner-time valuation, how site signals attach to findings)
- Then: backend site-read spec, report engine, landing pages, report templates

## Watch items
- The Jotform API lists fields in creation order, so the order must be verified visually in the editor
- Site-derived findings must be phrased as observations ("From your site, it looks like…"), never as facts
- Opt-in friction from the qualification questions is still worth watching once the form is live

## Key files
- [[20260923_stage-1-intake-form-design]] — full form spec, Jotform link, backend site-read plan and guardrails, and the remaining manual checklist. Open this for any form or engine work
- [[20260922_close-q4-strong-entry-offer]] — main offer note, Stage 1 Steps 1–7
- [[20260920_async-teardown-entry-offer]] — Stage 2 Teardown design
- [[20260910_capital-financing-opportunity-map-final]] — what the real Roadmap deliverable looks like
