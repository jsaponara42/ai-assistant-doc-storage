---
title: "Async Business Teardown — Paid Entry Offer"
date: 2026-09-20
tags: [idea, strategy, client]
ai: claude
status: needs-attention
---

## Summary

The current working direction for Blue Tusk's low-ticket funnel entry point: a personalized business teardown, paid ($500 value), waived if the prospect qualifies and completes intake "homework." Ends by pointing at the AI & Automation Roadmap as the upsell.

> **Delivery format updated 2026-09-22:** teardown is delivered as a **document**, not an async video, paired with a **live review call** where the Roadmap upsell happens (via Hormozi's CLOSER method — see rough outline below). This is a deliberate trade-off against the original "no live call, scales past JC's calendar" rationale below — JC has decided the upsell is worth the calendar cost. Worth keeping an eye on whether call volume becomes a bottleneck as this scales.

This is the leading candidate that emerged from a longer entry-offer exploration — see [[20260918_ai-power-user-course-funnel]] for the full reasoning trail (what was tried, what was rejected, and why this direction won). This note is where the async teardown itself gets designed and built out, separate from the broader funnel-strategy discussion.

## Concept

> **Updated 2026-09-22:** delivery is now a **document**, not a video (see Summary note above). Prospect submits their website/LinkedIn and a short intake (see below). Within roughly 48 hours, they receive a written teardown document with 2 to 3 concrete, specific observations about their business, followed by a **live review call** where JC walks through the findings and makes the Roadmap upsell.

### Rough upsell call outline (Hormozi's CLOSER method + "one step of a multi-step process" framing)
Not scripted in detail yet — rough shape only:
- **C**larify why they're on the call (review their teardown findings)
- **L**abel them as the right kind of business owner (already taking action on AI while peers hesitate)
- **O**verview their pain (recap the 2–3 findings — what it's costing them now)
- **S**ell the outcome, not the mechanism (paint what the business looks like once those opportunities are actually built out, before describing the Roadmap itself)
- **E**xplain the offer using the multi-step framing: the teardown found the opportunity (step one), the Roadmap is the rest — see working language in [[20260922_close-q4-strong-entry-offer]]
- **R**einforce their decision, address remaining doubts

## Why it clears the accumulated objections (from the parent funnel note)

- **Immediate** — 48hr turnaround to document delivery, review call scheduled separately
- **Feels bespoke/personal** — genuinely about their business, not generic content, without becoming an ongoing relationship or club/membership
- ~~**Async** — scales past JC's calendar, unlike a live call or cohort~~ *(no longer applies — review call now required; see delivery format update above)*
- **No integration with the client's live systems** — self-contained, no implementation tail, no testing against their real CRM/data
- **Natural upsell** — review call ends by pointing at the full Roadmap, using the multi-step framing

**Reuses existing capability**: built on the same underlying pipeline as the `pi-firm-snapshot` skill already in the vault (`business/SKILLS/pi-firm-snapshot/SKILL.md`).

**Not yet resolved**: the objection that audits/snapshots deliver knowledge, not progress (see parent note) still technically applies here. Softened by (a) being personal/reactive rather than a generic opportunity list, and (b) the price point and delivery format signaling status/attention rather than "go figure out your opportunities yourself." Worth stress-testing directly, ideally with real prospects, before scaling this up.

## Intake design — fast, high-signal, low-effort for the prospect

> **Resolved 2026-09-22** — the intake document/question set stays the same for everyone. The only difference is by path: **cold-qualified prospects** (came through Stage 1) get relevant fields pre-filled from their Stage 1 intake answers and are never re-asked — Stage 1's answers are a head start, not a substitute, since that form was kept light to protect free-magnet conversion and doesn't go deep enough for a $1,500-value teardown on its own. **Warm prospects** (skipped Stage 1) fill out the full intake fresh, as originally designed below.

> **Question set drafted 2026-09-22** — built backward from the locked Teardown document structure (see Document format section below), so every question serves a specific part of the final deliverable and nothing is asked without a use. See full question set and revision policy below, replacing the earlier placeholder "fixed set of questions."

### Revision policy
One round of follow-up allowed. Prospect submits their copy of the doc; JC marks it up / adds clarifying questions directly in the doc where an answer is too thin to build the Teardown from; prospect gets **one resubmission** before the Teardown gets built. Not unlimited back-and-forth — keeps this from becoming a scope-creeping back-and-forth on a $497 (or free/warm) offer.

### Question set

**Section 0 — Business basics** (feeds the opening reflection + qualification fields)
- Business name, website, what you do
- How long operating, approximate size (employee count or revenue range)
- What's prompting you to look at this now, going into Q4?
- If we find a real opportunity here, would investing in implementing it this quarter be realistic for your business? *(soft budget/willingness signal — same field folded into the Stage 1 form for cold-qualified prospects)*

**Section 1 — Business-unit snapshot** (feeds the business-unit coverage map — repeat once per unit: Account Management, Sales, Accounting, Back Office, Marketing, Product/Project Delivery)
- Does this function exist as its own role/department? Who owns it?
- In a sentence or two, how does work move through this area day to day?
- Any recurring frustration or bottleneck here? *(optional)*

Designed for team distribution — each section naturally maps to whoever owns that part of the business (sales lead answers Section 1's Sales block, bookkeeper answers Accounting, etc.), consistent with the team-distribution mechanic already established below.

**Section 2 — Deep dive** (feeds the 2–3 ranked opportunities — the core content of the document)
- Of the areas above, which 1–3 feel the most manual, frustrating, or time-consuming right now? *(respondent self-selects — this determines where the Teardown goes deep)*
- For each one flagged: describe the specific task step by step
- Who does it, and how many people are involved?
- How often does it happen, and how long does it take each time?
- What happens when it goes wrong, or what's the cost of it staying manual? *(lost customers, late payments, errors, compliance risk, etc.)*
- Any tool currently used for this? *(sanity-checks whether it's genuinely manual or already semi-automated)*

**Section 3 — Context** (feeds the opening reflection's specificity)
- What makes your business different from competitors in your space?
- Anything specific going on this quarter worth knowing? *(growth push, new hire, slow season, etc.)*

- **Pull public data first.** Anything gettable from their website/LinkedIn (reusing the `pi-firm-snapshot` pipeline) gets pulled automatically — never ask a question Google could already answer.
- **Delivery mechanic**: a Google Doc template with a fixed set of questions. The prospect makes their own copy and answers directly into each question using voice dictation rather than typing — faster and richer answers from busy executives, no custom voice-intake tooling required.
- **Team distribution encouraged**: prospect is told to send the doc around to their own team so specific people can answer the questions they personally know best. This gets real specificity into the intake without costing JC any extra time, and mirrors what's worked in real engagements (e.g., multiple stakeholders interviewed for the Capital Financing opportunity map — see [[20260910_capital-financing-opportunity-map-final]]).

## Pricing and qualification mechanic

> **SUPERSEDED 2026-09-22** — see [[20260922_close-q4-strong-entry-offer]], Step 2/Step 3. The offer this note describes is now Stage 2 of a 3-stage funnel. The flat "$500 value, free if qualified + homework" model below has been replaced by a traffic-path-split model: normal price $1,500; cold traffic (qualified via a new Stage 1 free-magnet intake form) gets it at **$497**; warm traffic (skipping Stage 1) still gets it **free**, gated by a separate, lighter qualification step still to be defined. Sections below are kept for historical context (intake design, homework concept) but the pricing figures are out of date.

- Structured as an introductory offer: **a $500 value**, positioned as "free" if the prospect completes certain conditions (their "homework").
- **Homework, resolved 2026-09-22:** just the intake doc (Google Doc, completed properly) — no referral requirement. Applies specifically to the **warm-traffic** free path: warm prospects get the teardown free only if they complete the homework (the intake doc). This keeps a commitment device on the free path so "it's free" doesn't turn into wasted time on either side. **Pricing presentation, added 2026-09-22:** positioned to the prospect as "$1,500 value, free for you" rather than just "free" — keeps the same anchor working on the warm path as the cold path, so it reads as a meaningful discount earned rather than a generic freebie.
- **Qualification gate**: prospects must qualify for the free offer — not open to anyone who wants a free teardown. Qualification requires collecting real information upfront: business size, and willingness/budget to eventually purchase the Roadmap. This does two things at once: keeps the free version from becoming a cost center on unqualified leads, and front-loads exactly the information needed to judge whether the Roadmap upsell is realistic before JC invests any time.
- **Qualified-but-incomplete, resolved 2026-09-22:**
  - **Cold path:** the $497 payment gates access to the full teardown intake itself — a cold-qualified prospect simply cannot start/complete the intake without paying first. No stalled free work; if someone pays and doesn't follow through, that's their choice and their money.
  - **Warm path:** the teardown is free but gated by completing the homework (intake doc). If a warm prospect doesn't complete it, they don't get the teardown — no exceptions, and no time spent chasing them. Incompletion itself is read as a signal they aren't a good fit for further engagement.
- This is JC's own resolution of three refund-mechanic options considered earlier (A: refund on completion, B: refund credited toward the Roadmap, C: refund if JC doesn't deliver value). The actual direction is closer to option A in structure (earn it back by completing conditions), reframed as "free upfront if qualified + homework done" rather than "pay then get refunded," combined with a hard qualification gate that wasn't part of the original three options.

## Open questions

- Full script for the review call beyond the rough CLOSER outline above

## Document format (locked 2026-09-22)

- **Format: PDF.** Chosen over a Notion page (like the existing `audit-report-notion` PI skill) because a polished branded PDF reads more like a premium paid deliverable, fitting the $1,500 anchor/$497 pricing — a shareable Notion link tends to feel more like an internal working doc. Trade-off noted: the `audit-report-notion` skill could be adapted with less rework if a Notion-based format is ever preferred instead.
- **Length: medium, roughly 3–5 pages** — room for context/explanation per opportunity, not just a bare list.
- **Structure**, adapted from the `audit-report-notion` skill's shape (Mermaid flowchart, scored quick-win tables, open-pain section, metrics upsell signal, next steps) and grounded directly in the real $7–10K Roadmap deliverable's DNA — see [[20260922_close-q4-strong-entry-offer]] for the full reasoning (effort/impact tiering, honest "what this is/isn't" framing, specificity over generic categories):
  1. Opening reflection — 1–2 sentences showing genuine, specific familiarity with their business, not generic
  2. **Business-unit coverage map** — a simple visual across standard categories (Account Management, Sales, Accounting, Back Office, Marketing, Product/Project Delivery) marking which unit(s) the findings actually touched, leaving the rest visibly unexplored. Replaces an earlier "full overview flowchart" idea, which isn't realistic to produce credibly from a single intake (the real Roadmap's overview diagram comes from 8 weeks of multi-stakeholder discovery). This map is honest about scope AND visually sells the Roadmap by showing how much of the business a full discovery process would cover.
  3. 2–3 ranked opportunities — each with "what we found" + dollarized/time impact (hours + dollars, per the Stage 1 Manual-Process Cost Estimate approach), scored Effort/Impact and tiered (Quick Win, Near-Term, Strategic, Needs Decision — same tier language as the real deliverable)
  4. "What this covers / what this doesn't" — explicit, mirrors the real deliverable's own "what this is/isn't" framing; sets up the review call/Roadmap naturally via the "one step of a multi-step process" framing
  5. Next step — pointer to the review call; no hard pitch inside the document itself

## Next steps
- [ ] Build the Google Doc intake template (fixed question set, designed for voice dictation, shareable with the prospect's team)
- [ ] Build the PDF document template per the locked structure above
- [ ] Draft the full review-call script beyond the rough CLOSER outline above
- [ ] Stress-test whether this still counts as "knowledge not progress" to the buyer, and how the personal/reactive framing + price point are meant to offset that
- [ ] Once mechanic is locked, run a small test batch with real prospects before scaling
