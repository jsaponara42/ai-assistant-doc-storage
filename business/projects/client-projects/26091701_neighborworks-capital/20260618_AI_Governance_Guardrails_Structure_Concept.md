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

## Executive Summary
*For leadership review and approval*

NeighborWorks Capital is beginning a structured, deliberate approach to AI adoption. This document defines how that happens safely.

The framework has four components:

**1. A clear position on AI and jobs.** The organization's stated intent is to use AI to free staff from repetitive, low-value work and redirect that capacity toward higher-value priorities — growing the lending pipeline, deeper analysis, stronger borrower relationships. This position is communicated explicitly and repeatedly so staff can engage with the initiative honestly rather than defensively.

**2. A channel for ideas and complaints.** Staff submit workflow frustrations through a low-barrier shared list — no justification required. A designated owner converts submissions into time or dollar estimates. Leadership reviews the prioritized backlog on a recurring cadence and decides what to act on. Nothing gets lost; nothing gets acted on without a decision.

**3. A tiered system for safe experimentation.** Staff can explore AI freely as long as no real organizational data is involved — no approval, no barriers. As data sensitivity increases, so does the approval requirement. High-sensitivity work and anything client-facing requires sign-off from the Chief Risk Officer. A designated group of AI champions has a faster lane for early-stage experimentation, enabling grassroots discovery without exposing the organization to data risk.

**4. A data and tool reference.** A single document tells any staff member exactly which tools are permitted for which types of data — and walks them through a step-by-step decision flowchart when the answer is not a simple yes or no. This replaces ad-hoc judgment calls with a consistent, documented standard.

**What leadership is asked to approve:**
- The principle that AI adoption is a capacity investment, not a headcount reduction — and the willingness to state this directly to staff.
- The tiered framework as the governing structure for AI use across the organization.
- The Chief Risk Officer as the sign-off authority for high-sensitivity and client-facing AI use.
- A recurring review of the prioritized idea backlog at an existing leadership forum (cadence to be confirmed).

The detailed structure behind each component follows in the sections below.

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

This matrix is the single source of truth for what data can go into which tool. Check it before starting any AI-assisted task that involves real NWC data. Cells marked **Conditional** are followed by a flowchart that walks you through the approval decision step by step.

**A note on data training:** "Free / personal AI accounts" covers any consumer-tier product — ChatGPT (free), Claude (free), Gemini (free), or similar. These tools train on user input by default and are **never permitted for any NWC data.** Microsoft 365 Copilot (paid, tenant-managed) does not train on organizational data by default — this is why it is the preferred tool for internal and borrower-related work.

---

### Tool columns

| Tool                        | What it is                                                               | Trains on your data?                                                                                                              |
| --------------------------- | ------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| Free / personal AI accounts | Any consumer-tier AI tool (ChatGPT free, Claude free, Gemini free, etc.) | **Yes** — never use with NWC data                                                                                                 |
| Microsoft Copilot (free)    | The free-tier Copilot experience available to Microsoft 365 users        | Unclear / not covered by enterprise terms — treat as risky                                                                        |
| Microsoft Copilot (paid)    | The Microsoft 365 Copilot tenant managed by NWC                          | **No** — Microsoft enterprise terms exclude org data from training                                                                |
| New / unevaluated tool      | Any tool not yet reviewed and approved by the AI/automation owner        | Unknown — must be evaluated before use with any NWC data. Enterprise agreements with Claude and ChatGPT don't train on your data. |

---

### The matrix

**Key:** ✓ Allowed ; ⚡ Conditional (see flowchart below); ✗ Never allowed

#### Group A — No real data (Tier 1 — anyone, no approval needed)

> *Examples of data in this group:*
> _(Add examples here — e.g. publicly available housing market statistics, made-up borrower names for testing, a draft email with no NWC-specific content)_

| Data type | Free / personal AI | Copilot (free) | Copilot (paid) | New / unevaluated tool |
|---|:---:|:---:|:---:|:---:|
| Public information & general knowledge | ✓ | ✓ | ✓ | ⚡ |
| Synthetic / made-up examples | ✓ | ✓ | ✓ | ⚡ |
| Your own writing with no NWC content | ✓ | ✓ | ✓ | ⚡ |

---

#### Group B — Internal organizational data (Tier 1.5 for champions / Tier 2 for all staff)

> *Examples of data in this group:*
> _(Add examples here — e.g. NWC lending policy documents, internal meeting agendas, draft staff communications, procedure guides)_

| Data type | Free / personal AI | Copilot (free) | Copilot (paid) | New / unevaluated tool |
|---|:---:|:---:|:---:|:---:|
| NWC policies & procedures | ✗ | ⚡ | ✓ | ✗ |
| Internal drafts & working documents | ✗ | ⚡ | ✓ | ✗ |
| Staff communications & meeting notes | ✗ | ⚡ | ✓ | ✗ |

---

#### Group C — Borrower-related data (Tier 2 → Tier 3 depending on use)

> *Examples of data in this group:*
> _(Add examples here — e.g. borrower organization names, credit memos stored in SharePoint, loan term sheets, draw request documentation, closing checklists)_

| Data type | Free / personal AI | Copilot (free) | Copilot (paid) | New / unevaluated tool |
|---|:---:|:---:|:---:|:---:|
| Borrower names & identifying details | ✗ | ✗ | ⚡ | ✗ |
| Credit memos & loan history (SharePoint) | ✗ | ✗ | ⚡ | ✗ |
| Loan terms & financial conditions | ✗ | ✗ | ⚡ | ✗ |
| Draw requests & closing documents | ✗ | ✗ | ⚡ | ✗ |

---

#### Group D — High-sensitivity data (Tier 3 — CRO sign-off required in all cases)

> *Examples of data in this group:*
> _(Add examples here — e.g. NWC's own audited financials, data being used as direct input to a credit decision, any output going to a borrower or external funder)_

| Data type | Free / personal AI | Copilot (free) | Copilot (paid) | New / unevaluated tool |
|---|:---:|:---:|:---:|:---:|
| NWC's own financial data | ✗ | ✗ | ⚡ | ✗ |
| Data entering a credit decision | ✗ | ✗ | ⚡ | ✗ |
| Client-facing or external output | ✗ | ✗ | ⚡ | ✗ |

---

### Conditional flowcharts

For every ⚡ Conditional cell in the matrix, follow the flowchart below that matches your situation. Work through each question top to bottom and stop when you reach an outcome.

---

#### FC-1: New / unevaluated tool — Group A data only (public / no real NWC data)

**Q1. Are you a designated AI team member (champion)?**

- **Yes →** You may use the tool for Tier 1 sandbox work only. No NWC data of any kind may be used. Log a brief note for the team on what you tried and what you found. ✓ Proceed.
- **No →** Stick to approved tools (Copilot) for now. Flag the new tool to the AI/automation owner — if it looks promising it can go through evaluation. ✗ Stop.

---

#### FC-2: Microsoft Copilot (free tier) — Group B internal data

**Q1. Are you a designated AI team member (champion)?**

- **Yes →** Permitted as a Tier 1.5 experiment with low-sensitivity internal data only (policies, procedures, meeting notes — nothing borrower-related). Document what you tried and report findings back to the team. ✓ Proceed.
- **No →** Use the paid Copilot tenant instead — it has the correct enterprise data controls. Free Copilot is not covered by NWC's Microsoft enterprise agreement. → Use paid Copilot.

---

#### FC-3: Microsoft Copilot (paid) — Group C, borrower names & identifiers

**Q1. Is the output for internal use only?**
*(i.e. an internal summary or draft note — not going to the borrower or any external party)*

- **Yes →** Permitted at Tier 2. If you are unsure whether this specific use case has already been approved, check with the AI/automation owner before proceeding. ✓ Proceed.
- **No →** This is Tier 3. A use-case write-up and CRO (Beth O'Leary) sign-off are required before proceeding. ✗ Stop — go to Tier 3 sign-off.

---

#### FC-4: Microsoft Copilot (paid) — Group C, credit memos & loan history

**Q1. Are you a designated AI team member (champion)?**

- **Yes →** Go to Q2.
- **No →** This use case is not yet open to all staff. Raise it through the idea pipeline. If it has already been approved, the AI/automation owner can confirm. ✗ Stop.

**Q2. Is the output for internal review only?**
*(Not going to the borrower or any external party)*

- **Yes →** Permitted at Tier 2 under the credit memo automation workstream. Use the approved Copilot tenant only. A qualified staff member must review the output before it is acted on. ✓ Proceed.
- **No →** Tier 3 required. Submit a use-case write-up to Beth O'Leary covering: the task, data involved, tool used, pros and cons, and the fallback if the AI output is wrong. Wait for explicit written approval. ✗ Stop — go to Tier 3 sign-off.

---

#### FC-5: Microsoft Copilot (paid) — Group C, loan terms, financial conditions, draw requests & closing docs

**Q1. Is this for internal drafting or summarisation only?**
*(Output stays inside the organisation)*

- **Yes →** Go to Q2.
- **No →** Tier 3. Use-case write-up and CRO sign-off required before proceeding. ✗ Stop — go to Tier 3 sign-off.

**Q2. Does the output feed directly into a credit decision?**
*(i.e. it is used as supporting evidence, not just background reading)*

- **Yes →** Tier 3 regardless of internal/external. Submit to Beth O'Leary. AI output must be reviewed and approved by a qualified staff member before it enters the decision record. ✗ Stop — go to Tier 3 sign-off.
- **No →** Permitted at Tier 2 for internal drafting and background use. A qualified staff member must review the AI output before it is acted on. ✓ Proceed.

---

#### FC-6: Microsoft Copilot (paid) — Group D, all high-sensitivity data

This data group requires Tier 3 sign-off in all cases. There is no conditional path to a lower tier.

**Required steps before proceeding:**

1. Write up the use case: the task, the data involved, the tool, the pros, the cons, and the fallback if the AI output is wrong.
2. Confirm that the output will be reviewed by a qualified staff member before it is used.
3. Submit the write-up to Beth O'Leary (Chief Risk Officer) and wait for explicit written approval.
4. Do not proceed until approval is confirmed.

✗ Stop — complete all four steps above before using AI with this data.

---

### Tier 3 sign-off: use-case write-up template

When a flowchart directs you to Tier 3, submit this to the Chief Risk Officer before proceeding.

| Field | Your answer |
|---|---|
| What is the task? | |
| What data is involved? | |
| Which tool will be used? | |
| What are the benefits? | |
| What are the risks or failure modes? | |
| What is the fallback if the AI output is wrong? | |
| Who will review the output before it is used? | |

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
