---
title: "Free-until-value fee curve"
date: 2026-07-28
tags: [idea, strategy, client]
ai: claude
status: needs-attention
---

## Summary
A pricing narrative for the free-consultation offer: instead of just saying "free," show prospects the shape of how the engagement fee evolves over time — free while barriers are cleared, then rising fast as measurable value compounds, then settling at a lower steady-state fee once the partnership is optimized. Reframes "free" from suspicious to strategic, and pre-sells the eventual invoice.

## Context
Captured from the tail end of a call (2026-07-28), riffing on how to pitch the free-workflow-audit offer without triggering the "what's the catch" hesitation that free offers usually create. Extended the next day with two comparisons against the alternatives a prospect is actually weighing: hiring in-house, and patchwork vendor engagements. Builds directly on the existing Free Workflow Waste Audit funnel (`business/projects/blue-tusk-go-to-market/`, `business/sales/`). The source inbox voice notes (`xx_needs-categorization/20260728_how-to-be-free`) have been folded into this note and removed from the inbox.

## Content

### The core insight
Offering something for free creates hesitation, not trust — prospects assume the "free" is hiding a future cost, and that ambiguity itself is what stalls action. The fix isn't to avoid mentioning the eventual fee — it's to show the shape of it up front, as a visual, so the prospect knows exactly what to expect and why.

### The curve (five stages)
1. **Free discovery** — $0. No invoice yet because there hasn't been enough access to remove the barriers (bad data, disconnected systems, unclear processes) standing between "nothing" and "measurable value." Charging here would be charging for friction, not value.
2. **First invoice** — the moment value becomes measurable, the first invoice goes out. Framed as a fixed reference point (e.g. "the first invoice tends to land around $5K/month") — no hard commitment, just a normed expectation so "free" doesn't sound like "free forever."
3. **Rapid growth** — as integration deepens (systems talk to each other, data becomes machine-readable, the team works fluidly with the engagement), the value created compounds, and fee rises to track it. This is presented as *good news*, not a warning — bigger fee = bigger, easier wins.
4. **Peak complexity** — the fee tops out at the point where the most coordination and build work is happening.
5. **Optimized partner** — once the systems are dialed in and running well, the fee drops to a steady-state (roughly a quarter to a half of peak) while the client keeps the full value indefinitely. The rationale given to the client: it's simply easier to work with them now, so that ease gets handed back as a lower fee — not because the value dropped.

### Why it works
- **Removes ambiguity, which removes hesitation.** "Free" alone invites a fear of hidden cost. Showing the curve replaces that fear with a concrete mental model.
- **Pre-frames the invoice.** By the time the first invoice arrives, the client already expects it and already has a rough number in mind — no sticker shock, no re-negotiation from scratch.
- **Aligns incentives visibly.** The fee only grows because value is compounding — the pitch explicitly ties the two together, so a rising invoice reads as proof of progress, not scope creep.
- **The final drop builds trust for the next deal.** Ending on "you keep the value, I lower the price" is a strong signal for referrals and renewals — it's the opposite of the usual vendor pattern (raise price once you're locked in).

### Pitch script (cleaned up from the source recording)
> "When I work with clients, this is usually what the fee structure looks like." *(show the curve)* "It starts free — for a few months, until we've figured out where I can create the most value for you. The moment that value becomes measurable, you get your first invoice — that's usually around $5K a month. From there, the more we integrate — the more your data and team can work smoothly with me — the faster that value compounds, and the fee grows to track it. Once we've dotted every i and crossed every t, working together gets so much easier that I bring the fee back down — to about a quarter or half of the peak — and you keep all the value we built, indefinitely."

### Why this beats the alternatives
Two comparisons worth having ready, since they're usually the prospect's actual alternatives to hiring you.

**vs. hiring someone full-time.** A hire is frontloaded *and* backheavy: you pay full salary from day one, before they're producing any value. As they prove themselves you give a raise — but you're already deep into the investment, so it doesn't feel optional. Once they clear the hardest ramp-up work, they typically get another raise. From there the cost only goes up, indefinitely, even after the hard part is behind you. You're fighting a cost curve that never comes down. This engagement is the mirror image: nothing upfront, cost rises only as value becomes measurable, and once the hard integration work is done, the fee drops back down instead of climbing forever.

**vs. patchwork vendors.** Hiring different vendors to bolt on one-off automations or tools, one at a time, means no one is holding a unified vision or direction for how the pieces fit together. That's cheap-looking at first, but it back-loads a much bigger cost: untangling everything that was built without a throughline once it needs to scale or connect. The lack of coordination shows up exactly at the high end — the point where things need to work together — and takes far longer to fix than it would have taken to build right the first time. A single engagement with a unified plan avoids that untangling cost entirely, because everything built along the way already assumes what comes next.

### Objection handling
- **"So it's not really free?"** — "Correct, and I'd rather tell you that up front than let you find out later. It's free until there's something worth paying for. I'm not going to invoice you for figuring out where your bottlenecks are."
- **"How do I know the fee won't keep climbing?"** — the curve itself is the answer: point to the drop-off stage. The fee has a ceiling built into the model, not an open-ended one.

## Next steps
- Turn the curve into a standalone visual asset (chart or simple diagram) for use in sales calls, the mini VSL, and the audit report deliverable — see `business/projects/blue-tusk-go-to-market/2026-04-03-Mini_VSL_prezo-free-workflow-waste-audit-agp.md` and `business/sales/2026-04-03-Mini_VSL_prezo-free-workflow-waste-audit-agp.md` as insertion points. A rough version was generated inline in chat on 2026-07-28 as a starting point.
- Build a second visual comparing this engagement's cost curve against the FTE-hire curve (frontloaded, never comes down) and the patchwork-vendor curve (zigzags between one-off tool purchases, then spikes when everything has to be untangled). A corrected version with real per-purchase volatility (not just a smooth peak) was generated inline in chat on 2026-07-28 — strong candidate for the "why not just hire someone" objection in sales conversations.
- Add the pitch script (above) as a beat in the call-flow SOP (`business/sales/2026-03-30-audit-call-flow.md`).
- Marketing angle: a short LinkedIn post walking through "why I show clients my fee curve before they ever pay me anything" — fits the existing story-post format in `business/marketing/writing/`. Good hook for the reciprocation/trust content already tracked in [[2026-06-01-reciprocation-lead-magnet]]
- Marketing angle: fold the curve into the free-workflow-audit one-pager (`business/marketing/materials/2026-06-05-free-ai-roadmap-one-pager.md`) as a visual proof point for how the free-to-paid transition works.
- Decide whether "$5K/month" stays as the stated first-invoice anchor or gets generalized — it's specific enough to be credible but should match current typical deal size.
- See linked task: [[20260728_build-free-until-value-fee-curve-asset]]