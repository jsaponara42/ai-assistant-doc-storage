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

## Problem statement

Why this offering matters *now*, stated plainly:

Agentic AI no longer just answers questions on demand — it works alongside a team, reading and reasoning over the company's actual files to do real tasks. That changes what file organization is *for*. It used to determine how long a human took to find something. Now it determines the quality of what the AI hands back:

- **If the organization is good, the AI gives its best-quality response** — it finds the right file, has the right context, and its output is trustworthy.
- **If it's bad, there are two distinct failure modes, not one:**
  1. **Wrong-place, confidently-wrong answers.** The AI looks in the wrong file or an outdated version and states the answer with full confidence — worse than a human saying "I couldn't find it," because nothing signals the answer might be wrong.
  2. **Real, compounding token cost.** Every extra search, re-read, or wrong turn the AI takes burns tokens. At individual-task scale that's invisible; at company scale, across every employee, every day, it adds up to thousands or tens of thousands of dollars a year in avoidable AI spend — a real, measurable line item, not a vague productivity loss.

This is the *AI-native* version of a problem that already existed for humans (see the pre-existing pain-point set in [[business/marketing/offers/20260814_file-chaos-marketing-angles]] — search time, version chaos, tribal knowledge). The AI-native version is worse, not better, because it's automated and scales with adoption: the more agentic AI a company rolls out on top of a messy filesystem, the more confidently-wrong answers and wasted spend they generate, faster than a human ever could on their own. **Better file organization is what converts agentic AI from a liability into the asset it's being sold as.**

## Content

### The offering stack

| Layer | What it is | Sale type | Moat / durability |
|---|---|---|---|
| 0. AI & Automation Roadmap | Existing flagship intro offer | One-time | Proven; unchanged by this direction |
| 1. Information Taxonomy design & migration | Folder structure, naming conventions, metadata schema, staff change-management, built specific to that company's actual chaos | One-time service | **The real moat.** Bespoke judgment work — every company's mess is a different mess. Not solvable by better AI alone. |
| 1.5. Packaged skills + navigation files | Custom skill library + routing/reference files that make traversal excellent — beyond the default the filesystem provider ships | Bundled with Layer 1, or subscription add-on | Only works well *because* Layer 1 exists underneath it. Differentiated on top of clean structure, generic on top of chaos. |
| 2. Taxonomy drift checker | Monitors new files/folders against the schema from Layer 1, flags or auto-corrects violations | Recurring subscription | **Bridge revenue, not permanent.** Platform vendors will likely absorb this into native AI features faster than they'll absorb Layer 1's judgment work. |
| 3. AI working-partner layer | **Draft-and-confirm.** As of 2026-10-07 this can happen *inside* Google Docs as tracked suggestions (see capability reality check) | Recurring subscription (seat/org-based) | Durable *only* on top of Layer 1. Should eventually integrate with the client's own platform AI rather than JC hosting everything long-term. |

### Why this beats the earlier "hosted AI copilot" direction
- Platform vendors are racing toward cheap, accurate, native file traversal and correct-placement writing — a hosted copilot competing on retrieval quality has a shrinking runway.
- Taxonomy design is bespoke judgment tied to a company's specific history — not something a platform vendor is incentivized to solve, and not something generic AI improvement fixes automatically.
- Much lower infrastructure/security burden than hosting a live "company brain" — directly resolves the security-posture and ops-burden objections raised in the prior adversarial pass on the hosted-system idea.

### Layer 1.5 detail — isolated Projects per workstream (a client behavior change, not a JC-built deliverable)

A real, sellable efficiency win that's available *today*, independent of any edit-in-place capability (see [[business/projects/internal/product/20260816_ai-file-integration-capability-reality-check]]): staff use a **separate, isolated Claude/ChatGPT Project per project/workstream** — not one shared project for everything — each scoped to its own path and its own context, so agents aren't burning tokens searching the whole filesystem on every task.

- **This is a habit the client's own staff adopts, not something JC configures or hands over per-project.** New projects start continuously; JC can't be the one spinning up a fresh Project every time one does. What JC actually delivers (as part of Layer 1 change-management / Layer 1.5) is the *pattern and the evergreen doc* — staff do the ongoing work of creating a new isolated Project each time and pointing it at that project's own path.
- Native Projects don't auto-scope a Drive/SharePoint connector to a folder — scoping happens by what's deliberately loaded into a project's custom instructions and reference material, not by restricting the connector itself. So each isolated Project needs two things loaded in: (1) the **evergreen doc** — a compact, org-wide conventions/map reference, the same one every Project gets, so agents have baseline orientation without re-deriving it — and (2) that Project's own scoped instructions naming its specific folder path(s)/file set.
- **Already validated internally, informally:** this is functionally what JC's own setup already does — a distinct project/context per workstream, `CONVENTIONS.md` as the shared evergreen doc across all of them, `xx_context-handoff.md` as the per-project scoped snapshot. The client version is the same shape and same behavior, just running on native Projects instead of a custom MCP server.
- Worth testing alongside the Layer 3 test: whether pasted-as-text project instructions genuinely outperform attached Drive docs for token cost/reliability (flagged as a live gap elsewhere) — that changes how the evergreen doc should actually be delivered, and how the training/guide teaches staff to set each Project up.

### Taxonomy is decided per client (JC, 2026-10-07)
There is no standard folder template to roll out. Each client's folder taxonomy is a JC design decision, made from that client's actual work, *before* any specific structure is suggested to them. That bespoke judgment is the Layer 1 moat. What can be standard across clients is the *pattern*:
- an evergreen conventions file at the root
- a project code per engagement
- a client brief as the anchor
- an AI working folder (below)

The folder names and structure around those elements are not standard.

### Per-client AI working folder (idea, JC 2026-10-07)
Each client or project folder gets an **AI-only working folder** (name to be decided per taxonomy, e.g. `_ai/`). It holds things that are for the agent, not for people:
- **Agent notes and memory:** working notes the agent keeps for itself across sessions.
- **Context handoff:** the client's `xx_context-handoff`-style snapshot, so any new session or any AI can pick up quickly. This is the same pattern as JC's vault.
- **Rough first drafts in markdown:** early drafts while decisions are still being made, before anything is shaped into a formatted, human-facing document.

**Why markdown here:** working in formatted Google Docs is token-heavy for agents. Every targeted edit needs a structural read of the document first, and the structural JSON is roughly 20–50x the size of the plain text. Formatting also gets in the way while content is still changing. The intended flow is to draft and iterate in markdown in the AI folder, then publish to a formatted Google Doc once the content is settled. After that, use targeted edits or suggestions for small changes. Humans can read the AI folder, but nothing in it counts as delivered or approved.

This idea needs testing: whether a native Claude Project can read and write its client's AI folder reliably, and how the folder fits each client's permission model (e.g. whether the assistant can see it).

**⚠️ Storage format UNRESOLVED (2026-10-07).** Real `.md` files in Drive can be created but not edited in place with the current connectors. The workaround, a plain Google Doc edited only through cheap paths, works, but structure reads still cost ~8K+ tokens even for tiny docs. JC is concerned about the long-run cost. Options A–F and the next checks are in [[business/projects/internal/product/20261007_google-drive-taxonomy-test-results]] (UNRESOLVED section). This matters for the offering too: a custom Drive-markdown MCP server (Option E) could be a Blue Tusk deliverable in its own right.

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
- **This boundary is a design choice, not a technical limit, as of 2026-10-07.** With Claude's Google Docs editor connector, Claude can edit existing Google Docs in place and in suggestion mode (tracked changes), and can do what a comment asks and reply in the thread. This was tested hands-on in [[business/projects/internal/product/20261007_google-drive-taxonomy-test-results]]. Draft-and-confirm stays, because clients' human gates require it, but it can now live inside the client's real documents instead of in separate draft files. SharePoint hasn't been re-tested; Claude's admin-gated write path from July 2026 is still the last known state. See [[business/projects/internal/product/20260816_ai-file-integration-capability-reality-check]] before pitching.
- **Sequencing:** transcripts next, CRM later. Both are real, priced setup work per client (defining what counts as a "decision" worth capturing is judgment work, not a solved NLP problem) — not a bundled free feature.
## Next steps
- [ ] Research migration execution strategy (parallel vs. incremental vs. big-bang) before the first engagement — blocking unknown.
- [ ] Draft the free taxonomy chart / DIY guide lead magnet.
- [ ] Define, concretely, what's delegatable to a hired PM vs. what stays JC-only — first offering with a real hiring case, worth a job-description-level breakdown.
- [ ] Revisit enterprise/PE sales-cycle objections specifically for this offering, given the lower infra/hosting burden changes the calculus from the earlier pass.
- [ ] Treat drift-checker pricing/positioning explicitly as bridge revenue, not a permanent product line.
- [ ] Name the offering / offering stack.
- [ ] Test native Claude/ChatGPT Projects (evergreen doc + scoped path instructions) against JC's own Drive setup — confirm the token/search-efficiency win is real before pricing it as part of Layer 1.5.


---

## Update 2026-10-08: the reference architecture

The offering stack now has a concrete, generalizable reference design: [[business/projects/internal/product/20261008_ai-native-operating-architecture]] (decisions: [[business/projects/internal/product/20261008_ai-native-architecture-decision-log]]). It was built for MOG and is meant for any firm, eventually Blue Tusk itself.

**How it maps to the layers:**
- **Layer 1 (taxonomy):** the identity scheme (3-letter client codes, `{CLIENT}-{YYMMDDNN}` project IDs), client-first Drive structure, and naming by audience. The folder taxonomy is still decided per firm (the bespoke part).
- **Layer 1.5 (navigation):** the System Registry, database ID tables, Drive INDEX, Summary properties for cheap catch-up, and a context-read skill (Company page + Project page).
- **Layer 3 (working partner):** draft-and-confirm made concrete. Notion holds drafts (measured roughly 15–200x cheaper to edit than Google Docs), Google Docs hold finals, and skills (draft, finalize, promote, intake, catch-up) enforce the rules.

**This answers the `_ai/` storage problem flagged above:** agent notes, handoffs and drafts live in Notion, not Drive.

**Possible offering components:**
- The reference architecture itself, as a productized build.
- The scripted backup and restore. It's relation-preserving, which Notion's native export isn't.
- Governance: System Registry, change protocol and locks, as the recurring "drift prevention" layer the free-tier note says stays paid.


### Commercial decisions (JC, 2026-10-08)
- **Backup is an ongoing paid offering** (AD-039). It's scripted, relation-preserving, with restore drills and drift checks, and it gives Blue Tusk ongoing stickiness.
- **Feature additions are Blue Tusk's ongoing role** (AD-040). Each build is customized, so Blue Tusk is the natural partner for new features, delivered through the governance layer (registry, change protocol, approved schema changes).
- **A simplified version becomes a free lead magnet** (AD-041). It's the same reciprocation pattern as the free-tier taxonomy principles: give away the shape, sell the build and the upkeep. What it includes is still open (O-10).
