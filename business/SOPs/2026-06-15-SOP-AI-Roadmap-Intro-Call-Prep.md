---
title: "SOP — AI Roadmap Consultation: Intro Call Prep"
date: 2026-06-15
last-updated: 2026-06-15
tags: [strategy, sales, ai-roadmap]
ai: claude
status: ok
---

# SOP — AI Roadmap Consultation: Intro Call Prep

## Summary

This SOP governs how to prepare for the initial intro call in the Free AI Roadmap Consultation offer. The consultation is industry-agnostic — prospects come from any sector — so the prep process must be adaptable while remaining systematic. The goal of prep is to walk into the intro call already knowing who you're talking to, what the company does operationally, and what pain points are most likely present before anyone says a word.

The AI-assisted implementation of this process is handled by the `ai-roadmap-call-prep` skill. Provide it with a company name, website, and the names and titles of the people attending, and it will execute all four stages and produce the Call Brief automatically. See [[business/SKILLS/ai-roadmap-call-prep/SKILL.md]].

This is the first documented version of this process.

## Previous Methods (Superseded)

This is the first documented version of this process.

---

## Current Process

The prep process runs in four stages: company research, person research, industry pain mapping, and call brief synthesis. Complete all four before the intro call. The full process takes 30–60 minutes depending on how much is publicly available about the company.

### Stage 1 — Company Research

**Goal:** Understand what the company does, how it operates, and where it likely has friction.

1. Look up the company website. Read the homepage, About page, and any services/products page. Note: what do they sell or deliver, who do they serve, how many people appear to work there, and how long have they been operating.
2. Search for the company on LinkedIn. Note headcount, department breakdown (are they heavy on admin, ops, sales, etc.), and any recent hiring patterns. Heavy recent hiring in admin or ops often signals manual process overload.
3. Search for the company on Google. Look for recent news, reviews (Google, Yelp, Glassdoor), and any press coverage. Negative reviews mentioning slow response times, disorganization, or communication issues are strong signals of ops pain.
4. If the company runs paid ads (Google Ads, Meta Ads), note it. Active ad spend means active lead flow — which often means intake and follow-up are under pressure.
5. Record the following in the Call Brief (Stage 4): company name, industry/sector, approximate size, primary service or product, how long in business, any signals of growth or strain.

### Stage 2 — Person Research

**Goal:** Understand who you're actually talking to and what their role means for the conversation.

1. Find the prospect on LinkedIn. Note their title, how long they've been in the role, and their background before this company. A founder or owner is a different conversation than a COO or ops manager — adjust accordingly.
2. Look for any content they've posted or engaged with publicly (LinkedIn activity, interviews, podcasts). This surfaces what they think about, what they're proud of, and occasionally what they're frustrated by.
3. Note how long they've been at the company. New leadership (under 18 months) is often actively looking to fix inherited problems. Long-tenured founders are often blind to their own bottlenecks.
4. If they have a public bio on the company site, read it. Note any language they use to describe themselves or their company — mirroring their own framing in the call builds rapport quickly.
5. Record the following in the Call Brief: prospect name, title, tenure, background, and any notable context about how they think or what they care about.

### Stage 3 — Industry Pain Mapping

**Goal:** Anticipate the most likely operational friction points before the prospect names them.

This stage is not about the specific company — it is about the industry they operate in. Every industry has structural inefficiencies that recur across firms of similar size. Knowing these in advance lets you ask sharper questions and recognize signals faster during the call.

1. Identify the industry category. Use broad categories: legal, healthcare, real estate, construction/trades, marketing/agency, financial services, professional services (accounting, HR, consulting), retail/e-commerce, hospitality, education, logistics/supply chain, nonprofit.
2. Run a brief research pass using the questions below as prompts. You do not need to write an essay — you need a short list of the 3–5 most common pain patterns for firms of this type and size.

   Prompts to guide your research pass:
   - What tasks in this industry are still done manually by default, even at firms that consider themselves modern?
   - Where does client or customer communication typically break down in this type of business?
   - What reporting, compliance, or documentation burdens are inherent to this industry?
   - Where do firms in this space typically lose revenue or time due to process gaps rather than strategy gaps?
   - What does a business in this industry typically look like at 5 people vs. 15 people vs. 50 people — and where does growth create new operational strain?

3. Use Claude or a quick web search if you don't already have strong familiarity with the industry. Frame the search as: "[industry] operational inefficiencies small business" or "[industry] workflow problems [firm size]".
4. Record the 3–5 most likely pain patterns in the Call Brief under "Anticipated Pains." Be specific. Not "communication issues" — but "clients going unanswered during intake because staff is handling active cases" or "estimates and proposals created manually in Word and emailed as PDFs with no tracking."

### Stage 4 — Call Brief Synthesis

**Goal:** Produce a single short document you can reference during or before the call.

Write a Call Brief using the template below. Keep it tight — this is a reference, not a report. You should be able to read it in under two minutes the morning of the call.

---

**CALL BRIEF TEMPLATE**

```
## [Prospect Name] — [Company Name]
**Date:** [call date]
**Industry:** [industry]

### The Company
- What they do: [1–2 sentences]
- Size: [approximate headcount]
- Stage: [startup / growth / established / mature]
- Notable: [anything that stood out — recent growth, reviews, ad spend, etc.]

### The Person
- Title: [title]
- Tenure: [how long in role]
- Background: [relevant prior experience]
- Notable: [any context about how they think, what they care about]

### Anticipated Pains
1. [Specific pain pattern #1 — tied to their industry and size]
2. [Specific pain pattern #2]
3. [Specific pain pattern #3]
(Add more if warranted — stop at 5)

### Sharp Questions to Ask
- [Question designed to confirm or surface Pain #1]
- [Question designed to confirm or surface Pain #2]
- [Question designed to confirm or surface Pain #3]
- [Open-ended question about what's taking the most time right now]
- [Question about what they've already tried]

### What to Listen For
[2–3 sentences on what a "good signal" sounds like in this conversation — what would tell you this is a strong fit for a full roadmap engagement]

### Red Flags
[Any context suggesting a mismatch — wrong stage, wrong problems, unlikely to act, etc.]
```

---

5. After writing the brief, read it once and ask: does this give you enough to lead a sharp 30-minute conversation? If not, identify what's missing and do a targeted search before the call.
6. Store the completed Call Brief in `business/projects/` under the prospect or company name. Do not store it in this SOPs folder.

---

## What to Track

After each intro call, note the following — either in the Call Brief file or in your task tracker:

- Did the anticipated pains match what the prospect actually named? (Yes / Partial / No)
- Which research stage was most useful?
- Were there questions that landed well or fell flat?
- What would you research differently next time?

This feedback loop improves the pain mapping in Stage 3 over time, especially as you accumulate pattern recognition across industries.

---

## What Is Not In Scope

- This SOP covers prep for the intro call only. The discovery session (call 2) and roadmap delivery (call 3) are separate processes not yet documented.
- This SOP does not cover how to run the intro call itself — conversation flow, agenda, and close are not defined here.
- This SOP does not cover lead sourcing or booking the call. See [[business/SOPs/2026-06-04-SOP-Warm-and-Cold-Reconnection-Outreach]] for the current reconnection outreach process.
- Industry pain patterns are not exhaustively documented here. Stage 3 relies on a live research pass rather than a static library. A separate reference document for common industry pain maps may be worth building once enough patterns have been validated.

---

## Next Review

Review this SOP after 10 completed intro calls. At that point there should be enough data from the tracking section to know whether the anticipated pains are calibrating well and whether any research stage is consistently adding little value. If industry-specific pain patterns are proving highly predictable, consider building out a separate reference library to replace the Stage 3 research pass.
