---
title: "AI Governance Guardrails — Structure Concept (NeighborWorks Capital)"
date: 2026-06-17
tags: [client, deliverable-concept, governance, neighborworks-capital]
ai: claude
status: needs-attention
---

# AI Governance Guardrails — Structure Concept
**For: NeighborWorks Capital**
**From: Blue Tusk**

> This is a structural concept for how NeighborWorks Capital can govern AI experimentation and adoption safely while still encouraging the team to surface ideas freely. It is designed to fit a risk-averse, finance-adjacent culture without slowing down the discovery of good use cases.
>
> Companion document: [[20260617_NeighborWorks_Capital_Brief]] (see Problem P-004 and Workstream D for how this fits into the overall engagement).

---

## 0. The Premise: What This Is For

Before any rules or tiers, the org needs a shared, explicit answer to the question sitting underneath all of this: **does AI take people's jobs, or does it give people back their time?**

The framing to lead with: smart people get hired because they're smart, and then often spend a meaningful share of their time on repetitive, low-judgment work that doesn't use that intelligence — a 30-page credit memo assembled by hand is a clear example already identified internally. AI's role is not to remove the person doing that work; it's to remove the *part of the job* that wastes their capacity, and return that time to higher-value work — customer engagement, growing the lending pipeline, deeper analysis. The organization benefits because its people are doing more of what they were actually hired to do, not because headcount shrinks.

This needs to be stated plainly and repeated, not implied once and forgotten: **the intent of this initiative is capacity reallocation, not reduction.** If leadership can affirm that directly (e.g., "if we get back 30–40 hours a week from automating X, here's what we'd do with that capacity — more pipeline coverage, maybe a new hire focused on a growth area"), say it out loud, because it's the single biggest lever against the fear that suppresses honest participation in everything below.

---

## 1. The Idea & Complaint Pipeline (the engine)

This is the mechanism that feeds the entire system. Without it, the tiers below have nothing to graduate from. The operating principle: **no complaint or idea is too small or too ridiculous to surface.** Filtering happens later, by leadership — not at the point of submission.

**Where ideas land:** A single, low-friction shared list (could be as simple as a running list in whatever tool the org already uses — Teams, SharePoint, etc.). The bar to add something must be close to zero.

**What a submission requires (minimum, by design):**
- What's the task or annoyance?
- Roughly how often does it happen?
- Roughly how long does it take?

That's it. The person submitting should not have to justify ROI or write a business case — adding that requirement filters out exactly the offhand, half-formed ideas that often turn out to be the most valuable.

**Who quantifies:** A designated owner (likely Tiana, or whoever holds the AI/automation function) periodically translates raw submissions into a comparable format — estimated time or money impact, e.g. "X takes ~3 hrs/week, affects ~Y people, ≈ Z hours/quarter." This is the translation layer between "I hate doing this" and "here's what fixing it is worth."

**Cultural note:** Treat surfacing complaints as a sanctioned, valued act — not venting, not negativity. This is a meaningful shift for a traditionally risk-averse team, and it should be named explicitly as a norm rather than left implicit.

---

## 2. Experimentation Tiers (with a champion fast lane)

Tiers are defined primarily by **what data is involved**, not by who's doing the work — with one exception (Tier 1.5) for designated champions. This keeps the gate proportional to actual risk instead of proportional to title or tenure.

### Tier 1 — Sandbox / Learning
- **Who:** Anyone.
- **What's allowed:** No real organizational, borrower, or client data. Public information, synthetic examples, general learning and tool exploration.
- **Approval needed:** None.
- **Purpose:** This is the deliberately low-stakes space where broad upskilling happens. The goal here is volume and noise — lots of people trying lots of small things, with zero cost to "failing." This is what produces the self-selecting AI champions the organization is already trying to identify.

### Tier 1.5 — Champion Fast Lane
- **Who:** Designated champions — people who've self-selected into the pilot group and demonstrated interest (consistent with the existing plan to require staff to request access and report back).
- **What's allowed:** A wider experimentation aperture than standard Tier 1 — for example, testing against de-identified or low-sensitivity real data, or earlier access to new tools ahead of general rollout.
- **Approval needed:** Minimal — light-touch check-in with the designated AI/automation owner, not a full sign-off.
- **Purpose:** The privilege here is speed and access, not reduced oversight. It rewards demonstrated engagement without loosening real data-risk controls. Champions still report back into the idea pipeline (Section 1), which is what turns their experiments into organizational value rather than isolated wins.

### Tier 2 — Internal Application
- **Who:** Anyone, once an idea has graduated past sandbox testing.
- **What's allowed:** Real organizational data, used internally, not client-facing. E.g., using AI to help summarize an internal credit memo draft for internal review.
- **Approval needed:** A check against the Data & Tool reference (Section 4) — confirming the tool's data handling is appropriate for the data type involved. This can sit with the AI/automation owner rather than requiring full leadership sign-off.
- **Purpose:** This is where most real productivity gains will actually happen. The gate here is "is this tool safe for this data," not "is this a good idea" — speed matters.

### Tier 3 — External-Facing or High-Sensitivity
- **Who:** Anyone, but requires sign-off.
- **What's allowed:** Anything that becomes client-facing, touches a credit decision, or that leadership would consider sensitive regardless of whether PII is involved (e.g., loan terms, organizational financials).
- **Approval needed:** A specific use-case write-up (task, data involved, tool, pros/cons, fallback if AI gets it wrong) presented to the Chief Risk Officer — mirroring the pattern that already works: bringing a well-researched, specific use case rather than an abstract request.
- **Purpose:** This is the highest-stakes tier and deserves real scrutiny. But because it's reached only after an idea has already proven itself in Tiers 1–2, what arrives here is pre-vetted, not speculative.

**The graduation path is the actual point of this structure.** An idea moves: Tier 1 (try it safely) → Tier 1.5 (champion validates it further, faster) → Tier 2 (apply it for real, internally) → Tier 3 (formalize it for external or high-sensitivity use, with sign-off). Nothing has to jump straight to "ask the Chief Risk Officer" — which is what currently makes asking feel heavy, and what likely discourages people from raising ideas at all.

---

## 3. Data & Tool Reference (the operational backbone)

A simple reference matrix — data types down one side, approved tools across the top, cells marked allowed / conditional / not allowed. This becomes the single source of truth that Tiers 2 and 3 check against, instead of re-deciding the same question every time a similar request comes up.

This is also the direct answer to the question already raised internally about whether company data trains a third-party model — each tool's entry in the matrix should state plainly what happens to data put into it.

> ⚠️ To be built once the full technology stack and each tool's data-handling terms are confirmed (see open items in the main client brief).

---

## 4. Quarterly Review Cadence

Leadership reviews the quantified idea backlog (from Section 1) on a recurring cadence and decides what to prioritize for the next quarter. To avoid creating a new standing meeting, this should be folded into an existing forum rather than run as a separate ritual — the IT steering committee (which already includes the CFO) is the natural fit, since it already touches technology decisions at the leadership level.

> ⚠️ NEEDS INPUT: Confirm how often the IT steering committee actually meets, and whether quarterly is a realistic cadence to attach this review to, or whether it needs its own slot.

---

## How the pieces fit together

1. **Premise** sets the tone — this is about capacity, not headcount.
2. **Idea pipeline** is the always-on input — nothing is too small to surface.
3. **Tiers** let people act on curiosity safely, with a faster lane for champions, without every idea requiring leadership's attention.
4. **Data & Tool reference** keeps Tier 2/3 decisions fast and consistent instead of re-litigated each time.
5. **Quarterly review** (folded into the IT steering committee) is where the backlog actually turns into decisions and resourcing.

---

## Open items

1. Confirm the IT steering committee's actual meeting cadence, and whether the quarterly review attaches to it or needs a separate slot.
2. Build the Data & Tool reference matrix once the full tech stack and each tool's data-handling terms are known.
3. Decide who owns quantifying submitted ideas day-to-day (proposed: Tiana, or the AI/automation function).
4. Decide the specific mechanism/tool for the idea-submission list (Teams channel, SharePoint list, form, etc.) — should be whatever has the lowest friction for this team.
