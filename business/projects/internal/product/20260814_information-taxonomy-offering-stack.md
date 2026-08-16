---
title: "Offering Stack — Information Taxonomy as Core Differentiator"
date: 2026-08-14
tags: [strategy, project, idea, offer]
ai: claude
status: needs-attention
---

## Summary
New offering direction: the AI & Automation Roadmap stays the intro/attraction offer, but **Information Taxonomy design & migration** becomes the core, differentiated upsell — this is the real moat identified across a multi-turn strategy session on 2026-08-14, replacing the earlier "hosted AI company-brain" direction as the primary product bet.

## Context
Follows the differentiation/scalability/adversarial-analysis thread earlier the same day. Core insight: JC's Claude setup works well not because of superior retrieval technology (which Microsoft Copilot, Google Gemini, and every platform vendor are racing to commoditize natively into SharePoint/Drive), but because JC's own information was made legible — conventions, folder structure, frontmatter, skill routing — *before* AI was ever pointed at it. Most companies' files are chaotic across tools, departed employees, and abandoned systems. That's an organizational/judgment problem, not a technology problem, and platform-native AI improvement doesn't fix it on its own.

Related: [[business/projects/internal/product/overview]], [[business/marketing/offers/20260814_attraction-offer-concepts]], [[business/ideas/2026-07-10-scaling-vault-to-team]]

## Content

### The offering stack

| Layer | What it is | Sale type | Moat / durability |
|---|---|---|---|
| 0. AI & Automation Roadmap | Existing flagship intro offer | One-time | Proven; unchanged by this direction |
| 1. Information Taxonomy design & migration | Folder structure, naming conventions, metadata schema, staff change-management, built specific to that company's actual chaos | One-time service | **The real moat.** Bespoke judgment work — every company's mess is a different mess. Not solvable by better AI alone. |
| 1.5. Packaged skills + navigation files | Custom skill library + routing/reference files that make traversal excellent — beyond the default the filesystem provider ships | Bundled with Layer 1, or subscription add-on | Only works well *because* Layer 1 exists underneath it. Differentiated on top of clean structure, generic on top of chaos. |
| 2. Taxonomy drift checker | Monitors new files/folders against the schema from Layer 1, flags or auto-corrects violations | Recurring subscription | **Bridge revenue, not permanent.** Platform vendors will likely absorb this into native AI features faster than they'll absorb Layer 1's judgment work. |
| 3. AI working-partner layer | **Draft-and-confirm, not edit-in-place** — see capability reality check below | Recurring subscription (seat/org-based) | Durable *only* on top of Layer 1. Should eventually integrate with the client's own platform AI rather than JC hosting everything long-term. |

### Why this beats the earlier "hosted AI copilot" direction
- Platform vendors are racing toward cheap, accurate, native file traversal and correct-placement writing — a hosted copilot competing on retrieval quality has a shrinking runway.
- Taxonomy design is bespoke judgment tied to a company's specific history — not something a platform vendor is incentivized to solve, and not something generic AI improvement fixes automatically.
- Much lower infrastructure/security burden than hosting a live "company brain" — directly resolves the security-posture and ops-burden objections raised in the prior adversarial pass on the hosted-system idea.

### Scalability & delegation — first real answer to "my product is me and my time"

| Stage | Requires JC specifically? | Notes |
|---|---|---|
| Sales / discovery / taxonomy design | **Yes** | This is the moat — stays bespoke, stays JC (or a senior hire eventually) |
| Bulk migration execution, drift-checker setup, staff training logistics | **No** | Genuinely delegatable to a hired project manager / ops hire once design is set |

- First offering in this whole strategy thread with a real structural seam for hiring — the Roadmap and the hosted-AI-system ideas both kept JC as the bottleneck end to end.
- Plausibly scales to large/enterprise companies, which earlier passes had deprioritized (long procurement cycles, solo-operator bus-factor risk). Worth revisiting specifically for this offering: enterprise companies likely have *more* file chaos, not less (legacy tools, M&A history, staff turnover), which could make them a better fit here even though they were a poor fit for the hosted-copilot idea. The sales-cycle-length objection from the earlier PE/enterprise adversarial pass isn't resolved by this and needs its own look.

### Open question — migration execution (JC's own flag: "this is going to absolutely suck")
Needs research before the first engagement — currently a blocking unknown, not a decided plan.

| Approach | Sketch | Risk/tradeoff |
|---|---|---|
| Big-bang cutover | Reorganize live, in place, on a set date | Highest risk of breakage/downtime; simplest to plan |
| Duplicate & parallel-run | Mirror the environment, build the new taxonomy in the copy, reconcile, then cut over in one day | Safer, but doubles storage/complexity temporarily; need a reconciliation process for anything that changed during the parallel period |
| Incremental, folder-by-folder | Migrate one department/project area at a time | Lowest risk per step, but taxonomy benefits arrive unevenly and takes longer to reach "done" |

### New lead magnet: free taxonomy chart / DIY guide
- Same reciprocation mechanic as the earlier Snapshot idea, applied to this offering: a free downloadable "how to build a file taxonomy yourself" guide, or a genericized taxonomy chart template.
- Fits the Decoy Offer model from the attraction-offers note: free/DIY guide as the decoy, paid migration engagement as the obvious premium ("who actually has time to do this properly").
- File under [[business/marketing/offers/20260814_attraction-offer-concepts]] once drafted.

### Funnel sequencing
Roadmap (intro) → Taxonomy design & migration (core paid engagement, main moat) → Drift-checker subscription (bridge recurring revenue) → AI working-partner layer (premium tier, ideally rides the client's own platform AI over time rather than JC hosting everything)


## Why RAG / knowledge-graph improvement doesn't undercut this
**Objection-handling material — not today's marketing angle.** Most buyers don't think in RAG/knowledge-graph terms yet, so lead with plain pain points (see [[business/marketing/offers/20260814_file-chaos-marketing-angles]]). Keep this in reserve for when a technically sophisticated prospect raises "won't better AI just solve this on its own?"

**Core distinction:** better RAG/KG retrieval solves whether an AI can *find* relevant content in a messy pile. It does not solve whether a *human* can browse, trust, verify, and be accountable for that content. The second half doesn't go away regardless of retrieval quality:

- **Compliance / legal discovery** requires defensible, categorized, access-controlled filing — a semantically-searchable blob doesn't satisfy an auditor or a court, no matter how good retrieval gets.
- **Access control requires structure by definition.** RAG doesn't remove the need to decide who can see what — it just hides that decision inside a vendor's permission model instead of a visible folder structure.
- **Provenance and trust** come from knowing where an answer came from and whether the context makes sense — not from retrieval quality alone.
- **Onboarding** is partly *learning where things live and how the business is organized* — a new hire who can only ever ask an AI ends up dependent, not competent.
- **Version/conflict resolution is a human-authorship problem.** People will keep creating duplicate and conflicting files regardless of how well AI can search across them; something still has to decide which one is canonical.
- **New risk, not a solved one:** a sensitive file buried in an old folder was safe by obscurity. Great retrieval makes it instantly surfaceable to anyone with technical access — this compliance/security argument gets *stronger* as retrieval improves, not weaker, and lands directly with the regulated-finance ICP.
- **Vendor lock-in:** "just let AI handle the blob" makes a company's entire operational memory hostage to one AI vendor's index, uptime, and pricing forever.

**Positioning takeaway:** don't build the pitch on "AI needs organized files to work well" — that claim has a shrinking shelf life as retrieval improves. Build it on "even perfect AI retrieval doesn't solve for compliance, accountability, onboarding, provenance, or vendor independence" — a claim that holds, or strengthens, as AI gets better.

## Expansion surfaces (future, sequenced — not yet in scope)

- **Meeting transcripts — higher priority than CRM.** Live-fed decision capture (transcript → drafted task/SOP update/note, human confirms before any write) directly answers the "goes stale" objection in the RAG section above, since it's fed continuously by every meeting rather than synced periodically. Positioned as the flagship use case for Layer 3 (AI working-partner), not a new numbered layer.
- **CRM/core systems — lower priority, harder integration surface.** Schema variance per client (Salesforce vs. HubSpot vs. custom) reopens the "narrow integrations only" discipline from Layer 1.5, and platform vendors are already building native AI on their own CRM data — less of an open gap than transcripts.
- **Both require the propose-don't-act boundary** — draft only, human confirms before any write to a live system. Transcripts raise the compliance bar further (personnel/negotiation content) for the finance-adjacent ICP.
- **This boundary isn't just a safety choice — it's currently the only version that's technically deliverable.** No major platform (Google Drive, SharePoint via ChatGPT) supports true edit-in-place today; Claude gained a narrow, admin-gated SharePoint write path in July 2026 only. See [[business/projects/internal/product/20260816_ai-file-integration-capability-reality-check]] before this gets pitched to anyone.
- **Sequencing:** transcripts next, CRM later. Both are real, priced setup work per client (defining what counts as a "decision" worth capturing is judgment work, not a solved NLP problem) — not a bundled free feature.
## Next steps
- [ ] Research migration execution strategy (parallel vs. incremental vs. big-bang) before the first engagement — blocking unknown.
- [ ] Draft the free taxonomy chart / DIY guide lead magnet.
- [ ] Define, concretely, what's delegatable to a hired PM vs. what stays JC-only — first offering with a real hiring case, worth a job-description-level breakdown.
- [ ] Revisit enterprise/PE sales-cycle objections specifically for this offering, given the lower infra/hosting burden changes the calculus from the earlier pass.
- [ ] Treat drift-checker pricing/positioning explicitly as bridge revenue, not a permanent product line.
- [ ] Name the offering / offering stack.
