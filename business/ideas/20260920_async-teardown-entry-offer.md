---
title: "Async Business Teardown — Paid Entry Offer"
date: 2026-09-20
tags: [idea, strategy, client]
ai: claude
status: needs-attention
---

## Summary

The current working direction for Blue Tusk's low-ticket funnel entry point: a personalized, async video teardown of a prospect's business, paid ($500 value), waived if the prospect qualifies and completes intake "homework." Delivered without any live call or integration into the client's systems, so it scales past JC's calendar. Ends by pointing at the AI & Automation Roadmap as the upsell.

This is the leading candidate that emerged from a longer entry-offer exploration — see [[20260918_ai-power-user-course-funnel]] for the full reasoning trail (what was tried, what was rejected, and why this direction won). This note is where the async teardown itself gets designed and built out, separate from the broader funnel-strategy discussion.

## Concept

Prospect submits their website/LinkedIn and a short intake (see below). Within roughly 48 hours, they receive a short, personally recorded (Loom-style) video where JC reacts to their specific business — 2 to 3 concrete, specific observations — ending in a clear next-step offer.

## Why it clears the accumulated objections (from the parent funnel note)

- **Immediate** — 48hr turnaround, no live call required, no waiting on a calendar slot
- **Feels bespoke/personal** — genuinely about their business, not generic content, without becoming an ongoing relationship or club/membership
- **Async** — scales past JC's calendar, unlike a live call or cohort
- **No integration with the client's live systems** — self-contained, no implementation tail, no testing against their real CRM/data
- **Natural upsell** — ends by pointing at the full Roadmap

**Reuses existing capability**: built on the same underlying pipeline as the `pi-firm-snapshot` skill already in the vault (`business/SKILLS/pi-firm-snapshot/SKILL.md`).

**Not yet resolved**: the objection that audits/snapshots deliver knowledge, not progress (see parent note) still technically applies here. Softened by (a) being personal/reactive rather than a generic opportunity list, and (b) the price point and delivery format signaling status/attention rather than "go figure out your opportunities yourself." Worth stress-testing directly, ideally with real prospects, before scaling this up.

## Intake design — fast, high-signal, low-effort for the prospect

- **Pull public data first.** Anything gettable from their website/LinkedIn (reusing the `pi-firm-snapshot` pipeline) gets pulled automatically — never ask a question Google could already answer.
- **Delivery mechanic**: a Google Doc template with a fixed set of questions. The prospect makes their own copy and answers directly into each question using voice dictation rather than typing — faster and richer answers from busy executives, no custom voice-intake tooling required.
- **Team distribution encouraged**: prospect is told to send the doc around to their own team so specific people can answer the questions they personally know best. This gets real specificity into the intake without costing JC any extra time, and mirrors what's worked in real engagements (e.g., multiple stakeholders interviewed for the Capital Financing opportunity map — see [[20260910_capital-financing-opportunity-map-final]]).

## Pricing and qualification mechanic

- Structured as an introductory offer: **a $500 value**, positioned as "free" if the prospect completes certain conditions (their "homework").
- **Homework under consideration**: completing the intake doc properly, and possibly referring 3 other qualifying businesses. Not finalized — JC is open to adding more conditions if useful.
- **Qualification gate**: prospects must qualify for the free offer — not open to anyone who wants a free teardown. Qualification requires collecting real information upfront: business size, and willingness/budget to eventually purchase the Roadmap. This does two things at once: keeps the free version from becoming a cost center on unqualified leads, and front-loads exactly the information needed to judge whether the Roadmap upsell is realistic before JC invests any time.
- This is JC's own resolution of three refund-mechanic options considered earlier (A: refund on completion, B: refund credited toward the Roadmap, C: refund if JC doesn't deliver value). The actual direction is closer to option A in structure (earn it back by completing conditions), reframed as "free upfront if qualified + homework done" rather than "pay then get refunded," combined with a hard qualification gate that wasn't part of the original three options.

## Open questions

- Exact homework requirements — just the intake doc, or also referrals, and if referrals, how many and how verified?
- Exact qualification questions/thresholds — business size cutoff, and how to ask about Roadmap budget/willingness without being off-putting this early?
- The actual cash mechanic — is the $500 ever charged upfront and refunded/waived, or simply waived entirely for qualified + homework-complete prospects? These have different cash-flow and commitment-device implications.
- What happens to a qualified prospect who doesn't complete the homework — do they still get the teardown at a paid price, or are they excluded entirely?
- Video format/length and exactly what it should cover per business
- The exact upsell moment/script into the Roadmap on the follow-up call

## Next steps
- [ ] Decide exact homework requirements (intake doc only, vs. also referrals — and if so, how many / how verified)
- [ ] Define qualification questions and thresholds (business size cutoff, how to ask about budget/willingness to buy the Roadmap without being off-putting this early)
- [ ] Decide the actual cash mechanic (charge-and-refund/waive vs. simply waived for qualified + homework-complete prospects)
- [ ] Decide what happens to qualified prospects who don't complete the homework
- [ ] Build the Google Doc intake template (fixed question set, designed for voice dictation, shareable with the prospect's team)
- [ ] Define video format/length and exactly what it covers per business
- [ ] Draft the upsell moment/script into the Roadmap on the follow-up call
- [ ] Stress-test whether this still counts as "knowledge not progress" to the buyer, and how the personal/reactive framing + price point are meant to offset that
- [ ] Once mechanic is locked, run a small test batch with real prospects before scaling
