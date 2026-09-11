---
title: "Capital Financing — AI & Automation Opportunity Map"
date: 2026-09-10
tags: [client, project, deliverable, ai, automation]
ai: claude
status: draft
---

> **INTERNAL DRAFT — not client-ready.** This still has internal source citations (want numbers, workflow-map links, effort/impact judgment calls) that need to be scrubbed or softened before this goes anywhere near Howie, Christy, Danielle, or Yasmine. Treat this as the working version of Proposal deliverables **#3 (Opportunity Map)** and **#4 (Quick Wins)** — see [[20260806_proposal-capital-financing-ai-automation-mapping]]. The full current-state process detail lives in [[20260616-Workflow-Map-Capital-Financing-merged]] and stays the living reference; this document is the curated, prioritized, presentation-facing layer built on top of it.

# Capital Financing — AI & Automation Opportunity Map

## What this document is for

This is the answer to "where should we actually spend automation effort, and why." It's built from eight weeks of discovery — the full workflow map, Howie's dictated wants, and direct 1:1s with Christy, Yasmine, and Kaz. **The value here isn't new discovery** — it's turning eight weeks of scattered calls, dictations, and half-formed ideas into one scored, ranked framework that's consistently applied, so priority never has to be re-litigated from scratch every time a new idea comes up.

**How to use it going forward:** whenever a new idea comes in (from Howie, from a call, from anywhere), the first move is to check whether it already lives here. If it does, it gets folded into the existing opportunity rather than treated as something new. If it doesn't, it gets scored against the same framework below and slotted in — either onto the main map, or into the backlog appendix until it's scoped enough to promote. This is what keeps Howie's stream of new ideas from turning into scope creep: everything gets measured against the same yardstick, in one place.

**What this is not:** a build spec. Nothing below prescribes exact tools, screens, or technical architecture. The point is to identify *where* the highest-opportunity, highest-ROI areas are and *what kind* of solution would plausibly fit — a rules engine, an adoption push, a sync job, an AI-assisted layer — not to design it.

**What this doesn't cover yet:** this map is weighted toward intake, underwriting, and sales, because that's where discovery has gone deepest so far. Yasmine's Contracting/Funding/Payouts process is already well-SOP'd and largely represented through Opportunity #6 below, and Danielle's controller/finance role isn't represented as its own opportunity at all yet. That's a gap in this pass, not a judgment that those areas don't matter — a dedicated look at controller- and contracting-specific automation is still owed once those 1:1s are fully synthesized.

---

## The Framework

Every opportunity is scored on two axes and sorted into one of four tiers.

**Effort** — Low / Medium / High. Rough build lift: Low = adoption/training or a small config change; Medium = a defined, scoped build (days, not weeks); High = a multi-phase build or one that depends on other unresolved pieces.

**Impact** — Low / Medium / High. Rough business value if it worked: revenue protected or unlocked, staff time freed up, or a load-bearing risk (single point of failure, compliance exposure) reduced.

| Tier | Meaning |
|---|---|
| 🟢 **Quick Win** | Low effort, ready or nearly ready to switch on now. |
| 🔵 **Near-Term** | Real build, but scoped and sequenced — next up once quick wins land. |
| 🟣 **Strategic** | High effort, high impact — multi-phase, needs real design work. |
| ⚪ **Needs Decision First** | Not yet buildable — blocked on a decision, missing information, or someone else's timeline (Kaz, Christy's SOP content, an org/economics call). |

**One honest gap in this framework:** Effort and Impact are scored qualitatively (Low/Med/High), not in dollars or hours. That's deliberate — inventing precise figures we don't have would be less honest than a clear qualitative call, and none of the calls so far have produced reliable time/cost baselines. Getting real numbers (hours currently spent on manual servicing check-ins, cost per unfilled Opportunity record, etc.) is a concrete next step, not something this version pretends to already have.

---

## Foundational note: systems architecture is already decided

Two opportunities below (Servicing Automation and Intake/Underwriting Structuring) sit on top of a systems decision that's already been made, not something still open: **Salesforce stays the CRM and system of automation/reporting; Segway is being adopted only for the ops/finance staff who need its financial-software features (~6 people), with an integration bridging the two.** This isn't itself ranked as an opportunity — it's context that keeps the items below from looking more uncertain than they are.

### If you only do three things

The numbering below is for reference, not priority order — tier and impact carry the actual ranking. If nothing else moves forward, these three matter most: **#1 (sales adoption)** because it's paid-for and unused, **#2 (referral portal)** because it's already in motion, and **#6 (servicing/AR/payoffs automation)** because it's the single largest headcount-leverage opportunity on this entire map, independently flagged by both Howie and Christy.

---

## A. The Opportunity Map

### Overview

```mermaid
flowchart LR
    classDef quickwin fill:#d1fae5,stroke:#059669,color:#065f46
    classDef nearterm fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    classDef strategic fill:#ede9fe,stroke:#7c3aed,color:#4c1d95
    classDef decision fill:#f3f4f6,stroke:#6b7280,color:#374151,stroke-dasharray: 4 3

    Ref[Referral Received] --> In[Intake Call and Docs]
    In --> UW[Underwriting]
    UW --> Ct[Contracting and Agreement]
    Ct --> Fd[Funding and Disbursement]
    Fd --> Sv[Servicing: AR, Payoffs, Close]

    Lead[Lead Assigned] --> Fol[Consultant Follow-Up]
    Fol --> Opp[Opportunity Tracked in CRM]
    Opp --> Ct

    Mkt[Outbound and Nurture] --> Lead

    In -.-> O1(["Structured intake +\nhard-rule auto-decline"])
    UW -.-> O1
    Ct -.-> O2(["Referral portal +\nfollow-up automation"])
    Sv -.-> O3(["Servicing automation"])
    Fol -.-> O4(["CRM adoption:\nOpportunity rollout"])
    Opp -.-> O5(["Slack + AI digest"])
    Mkt -.-> O6(["Outreach automation\nor role decision"])

    class O1 strategic
    class O2 quickwin
    class O3 strategic
    class O4 quickwin
    class O5 nearterm
    class O6 decision
```

### Priority summary

| # | Opportunity | Tier | Effort | Impact | Likely Owner |
|---|---|---|---|---|---|
| 1 | Sales follow-up & pipeline adoption | 🟢 Quick Win | Low | High | Howie (sales team) + Kaz |
| 2 | Referral/case-submission portal | 🟢 Quick Win | Low–Med | High | Christy's team |
| 3 | Slack + exception-based digest | 🔵 Near-Term | Med | High | Kaz |
| 4 | Referral-gap detection & firm follow-up | 🔵 Near-Term | Med | High | Kaz |
| 5 | Salesforce → MailChimp sync | 🔵 Near-Term | Low–Med | Medium | Kaz |
| 6 | Post-funding servicing/AR/payoffs automation | 🟣 Strategic | High | High | Yasmine + Kaz |
| 7 | Intake & underwriting structuring | 🟣 Strategic | Med–High | High | Christy |
| 8 | Howie's inbox AI assistant | 🟣 Strategic | Med–High | High | Howie + JC |
| 9 | Internal staff FAQ assistant | 🟣 Strategic | Medium | Med–High | Christy + JC |
| 10 | Outbound outreach: automate-or-retire the role | ⚪ Needs Decision | — | Medium | Howie |
| 11 | Conference list automation & territory structure | ⚪ Needs Decision | High | Medium | Howie |
| 12 | SharePoint information architecture & adoption | 🟢 Quick Win | Low–Med | High | JC (design) + Christy (rollout) |

---

### 1. Sales follow-up & pipeline adoption — 🟢 Quick Win

**The pain:** Consultants aren't consistently following up, and there's no visibility into who's working what. The fix for most of this **already exists** — a full Opportunity object with case-expense/pre-settlement-specific stages and automated task/notification logic (7-day no-meeting trigger, 30-day no-referral trigger) was already built in Salesforce, but it hasn't been adopted as a working habit yet, so it has no data to act on. Same story with the KPI dashboard: built, reviewed once, not yet rolled out day-to-day.

**The opportunity:** this is almost entirely an adoption problem, not a build problem. Make Opportunity creation a required, trained habit; turn the existing KPI dashboard back on; and deliver Howie a standing Monday-morning summary of each consultant's activity so he's not manually digging for it.

```mermaid
flowchart LR
    classDef quickwin fill:#d1fae5,stroke:#059669,color:#065f46
    A[Lead Assigned] --> B[Consultant Follow-Up]
    B --> C[Opportunity Record Created]
    C --> D[Auto Task / Notification Logic]
    D --> E[Outcome Logged]
    C -.->|already built, unused| Opp1(["Require Opportunity\ncreation as a habit"])
    B -.-> Opp2(["Monday-morning\nKPI digest"])
    class Opp1 quickwin
    class Opp2 quickwin
```

*Solution shape:* training + enforcement, not new development; a scheduled report/dashboard view once habits are in place.

---

### 2. Referral/case-submission portal — 🟢 Quick Win

**The pain:** Firms submit case documentation via a Word document Howie himself has called "unappealing, overwhelming, and unprofessional." This is Howie's own stated #1 business-loss concern.

**The opportunity:** replace the Word doc with a branded, firm-specific web form (unique link per firm) with validation, document upload, and auto-notifications — already in motion as a low-risk build with Christy's team.

```mermaid
flowchart LR
    classDef quickwin fill:#d1fae5,stroke:#059669,color:#065f46
    A[Onboarding Call Complete] --> B["Follow-up email,\n6 attachments, Word doc"]
    B --> C[Firm fills out & emails back]
    C --> D[Manual re-entry into CRM]
    B -.->|replace| Opp1(["Branded web form\n+ installable app"])
    class Opp1 quickwin
```

*Solution shape:* a form tool (already chosen), eventually installable as a lightweight app so firm staff don't lose the link.

---

### 3. Slack + exception-based digest — 🔵 Near-Term

**The pain:** Howie navigates roughly 100 Salesforce reports to find what matters, and largely doesn't — he's said directly he wants information pushed to him, not something he has to go seek out. The Slack subscription is already purchased; the AI-summarization layer on top isn't built yet.

**The opportunity:** an exception-based daily/weekly digest — who's gone inactive, what's stalled, what needs Howie's attention — delivered where the team already is. Sequenced after Opportunity #1 lands, since the digest needs real data to summarize.

```mermaid
flowchart LR
    classDef nearterm fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    A[CRM Activity Data] --> B[Digest Logic]
    B --> C[Slack Channel / DM]
    A -.-> Opp1(["AI-generated\nexception summary"])
    class Opp1 nearterm
```

*Solution shape:* a scheduled summarization layer reading CRM data, delivered via the Slack integration already in place.

---

### 4. Referral-gap detection & automated firm follow-up — 🔵 Near-Term

**The pain:** A firm gets onboarded, excited, and often never sends its first case — or sends one and goes quiet. No structured mechanism currently catches this.

**The opportunity:** a defined multi-touch sequence keyed off CRM timestamps (last referral, last call, last email) with automatic escalation if a firm goes cold, rather than relying on someone remembering to check in.

```mermaid
flowchart LR
    classDef nearterm fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    A[Firm Onboarded] --> B["Manual follow-up,\nif it happens"]
    B --> C[Weeks pass, no referral]
    C --> D[Firm goes quiet]
    B -.-> Opp1(["Automated multi-touch\nsequence + escalation"])
    C -.-> Opp1
    class Opp1 nearterm
```

*Solution shape:* an extension of the same Opportunity/task automation pattern already built for #1 — timestamp-triggered tasks and templated touches, not a new architecture.

---

### 5. Salesforce → MailChimp sync — 🔵 Near-Term

**The pain:** Warm-audience marketing runs through MailChimp now, but getting a current contact segment (active/inactive/prospect) there is a fully manual monthly CSV export-and-upload.

**The opportunity:** automate the sync so it doesn't depend on someone remembering to run it, with segment tags preserved on the MailChimp side.

*Solution shape:* a scheduled export or direct API sync between the two systems — one-directional, no new segmentation logic needed.

---

### 6. Post-funding servicing/AR/payoffs automation — 🟣 Strategic

**The pain:** Multiple staff spend real time on manual, discretionary check-in emails to law firms on active cases, purely to track status toward settlement. Both Howie and Christy have independently called this function fully automatable — Howie's own words: "we have real people doing things that could just be sending emails out and getting AI emails out to lawyers, checking in on them."

**The opportunity:** automated, cadence-based status-check outreach with reminders, freeing staff to work exceptions rather than routine check-ins.

```mermaid
flowchart LR
    classDef strategic fill:#ede9fe,stroke:#7c3aed,color:#4c1d95
    A[Funded Case] --> B["AR Tracking\n(manual check-ins)"]
    B --> C[Payoff / Reduction Request]
    C --> D[Deposit Received]
    D --> E[Reconciled & Closed]
    B -.->|"multiple staff,\nmanual status-check emails"| Opp1(["Automated status-check\n+ reminder cadence"])
    class Opp1 strategic
```

*Solution shape:* the highest-headcount-leverage item on this map — a cadence-and-template engine, likely bridging Salesforce and whichever system holds the lien/case record. Real design work, not a quick config change.

---

### 7. Intake & underwriting structuring — 🟣 Strategic

**The pain:** Underwriting has two distinct layers — a rules-based layer (state law, case type, eligibility) and a judgment layer (attorney/firm reputation, gut read) — but today, every case reaches Christy for review regardless of which layer it actually needs. This is also the single biggest blocker to the Segway build, which needs the intake questionnaire structured before it can be customized.

**The opportunity:** structure the rules-based layer as a defined questionnaire with hard-rule checkpoints, so a case that clearly fails never needs to reach Christy at all — freeing her time for the judgment calls only she can make.

```mermaid
flowchart LR
    classDef strategic fill:#ede9fe,stroke:#7c3aed,color:#4c1d95
    A[Client Interview] --> B[Case Facts Gathered]
    B --> C[Underwriting Review]
    C --> D{Rules Pass?}
    D -- No --> E["Still routes to Christy\ntoday, every time"]
    D -- Yes --> F["Judgment / gut call\n(Christy's real value)"]
    D -.-> Opp1(["Structured questionnaire\n+ hard-rule auto-decline"])
    class Opp1 strategic
```

*Solution shape:* a decision-tree-style intake questionnaire (client and law-firm facing) feeding a rules engine, not a full underwriting-AI build — the judgment layer stays human by design. **Gated on the underlying intake/underwriting content being written down** — see the backlog note below.

---

### 8. Howie's inbox AI assistant — 🟣 Strategic

**The pain:** Howie personally fields 200–300 emails/day, a meaningful share of which shouldn't be his (staff/HR questions that should go to Christy, case intake that should go to the team) or are low-value overhead (redundant status reports, repeated approval loops).

**The opportunity:** already fully specified by Howie himself — a suggest-don't-auto-forward triage layer, draft-shortening help, and aging-email flags, working inside his existing inbox with no folders or rules (his explicit hard constraint).

*Solution shape:* an in-line, suggestion-based assistant layered on Outlook — not an auto-sort/auto-file system, which he's explicitly ruled out.

---

### 9. Internal staff FAQ assistant — 🟣 Strategic

**The pain:** Standard staff questions (PTO process, intake procedure) route to Christy or Howie directly, or get lost in a disorganized SharePoint. Both Christy and Howie have independently proposed roughly the same idea.

**The opportunity:** a retrieval-based Q&A layer over the company's actual documentation, with SharePoint remaining the source-of-truth library underneath it.

*Solution shape:* straightforward once the underlying content exists — **this is gated on Christy's SOPs/FAQ material actually being written**, not a technical blocker.

---

### 10. Outbound outreach: automate-or-retire — ⚪ Needs Decision First

**The pain:** Current cold outreach produces effectively zero substantive replies at real volume (documented: 160 sends in a day, zero real responses), and the staffing cost isn't clearly justified.

**The opportunity:** either automate the cadence properly or retire the function — but this needs a people/role decision from Howie before it's a build question.

*Solution shape:* not scoped until the role decision is made.

---

### 11. Conference list automation & territory structure — ⚪ Needs Decision First

**The pain:** Matching new conference contacts against ~25,000 existing Salesforce contacts is a manual, ~2-hour-per-list task with only ~50% auto-match; assignment to consultants is also manual and untracked.

**The opportunity:** automate matching and assignment — but assignment logic depends on defining consultant territories first, which is an organizational/economics decision, not a technical one.

*Solution shape:* not scoped until the territory question is resolved.

---

### 12. SharePoint information architecture & adoption — 🟢 Quick Win

**The pain:** Company-wide file organization is genuinely poor — not a preference issue between tools, but a real gap independently flagged by multiple people on the leadership team. Sensitive documents (bank reporting) reach the CEO only via one-off email attachments, with no shared access at all. Different parts of the team default to different systems out of habit, and even where SharePoint is already in use, there's no consistent folder structure or naming convention, which makes it hard to trust or navigate.

**The opportunity:** this is **decided, not open** — SharePoint is the company-wide system going forward. What's still needed is the actual information architecture: a defined folder taxonomy, naming conventions, and governance rules, plus a real migration and change-management push to get everyone (including team members currently attached to other habits) onto one consistent structure. This is deliberately scoped as foundational, not a full automation build — but it's the base every future document-facing automation depends on, including a staff-facing FAQ assistant (Opportunity #9) or any future direct connection between Claude and the company's documents for search, summarization, or drafting. That connector work is a natural next phase once the taxonomy exists — not something to build before the foundation is in place.

*Solution shape:* an information-architecture and change-management project — taxonomy design, migration, and adoption habits — not a software build. Simple and contained relative to everything else on this map, which is exactly why it's well-suited to be a fast, visible win.

---

## B. Quick Wins (ready to move on now)

Per the proposal, quick wins are a possibility surfaced by discovery, not a promise — these two are the ones that actually clear that bar:

1. **Sales follow-up & pipeline adoption (Opportunity #1 above).** Zero new build — this is turning on and enforcing use of automation that's already been paid for and built. Highest-leverage single move available on this entire map.
2. **Referral/case-submission portal (Opportunity #2 above).** Already scoped and in motion with Christy's team on a low-risk, low-cost tool. Needs a check-in to confirm it's actually moving, not a new decision.
3. **SharePoint information architecture & adoption (Opportunity #12 above).** No build required — taxonomy design plus a real rollout push. Worth calling out specifically as a strong, low-risk opener for a follow-on engagement: contained, visible, and it's the foundation several other opportunities on this map (and future ones) will eventually depend on.

Everything else on the map is a real build or a pending decision — sequencing them is the next conversation, not something to promise before it's scoped.

---

## C. How new ideas get added

1. **Check if it's already here.** Most of what Howie brings up in the moment maps onto one of the eleven opportunities above, sometimes as a new detail on an existing one rather than something new.
2. **If it's genuinely new,** score it: Effort (Low/Med/High), Impact (Low/Med/High), using the same definitions as the framework above.
3. **Tier it** using the same logic — Quick Win, Near-Term, Strategic, or Needs Decision First.
4. **Slot it into the backlog appendix below** with its source and date. It only gets promoted onto the main map once it's scoped enough to sit next to the other eleven — a one-line idea doesn't jump straight to the priority table.

This is the mechanism for keeping Howie's stream of new ideas from becoming scope creep: everything gets measured the same way, in one place, instead of each new idea getting its own ad hoc conversation about whether it matters.

---

## Appendix: Full Backlog

Everything tracked that isn't on the curated map above — either too early-stage to score confidently, or minor enough not to warrant a headline slot. Full detail lives in [[xx_howies_wants]].

| Item | Tier | Note |
|---|---|---|
| AI-readable LinkedIn/Facebook bio (want #1) | 🟢 Quick Win (minor) | Zero-build, low-impact housekeeping — a prompt Howie runs himself. |
| Move training videos off Vimeo (want #2) | 🟢 Quick Win (minor) | File migration/reorg, no technical build. |
| Team-wide AI notetaker (want #3) | 🟢 Quick Win (minor) | Tool selection + rollout; adoption is the real work, not the tool. |
| Julius repositioned as personal assistant (want #12) | ⚪ Needs Decision | Depends on the outreach automate-or-retire call (Opportunity #10) landing first. |
| KPI dashboard improve-vs-leave-as-is call (want #13) | ⚪ Needs Decision | Requires a direct review with Kaz before recommending either way. |
| Consultant dashboard / weekly reporting layer (wants #16, #17) | 🔵 Near-Term | Downstream of Opportunity #4 (referral-gap detection) — sequence after, not before. |
| Territory-based FC structure (want #9) | ⚪ Needs Decision | Org/economics decision; blocks Opportunity #11. |
| Commissions-spreadsheet automation (want #7) | 🔵 Near-Term | Overlaps with Opportunity #1 — scope together once CRM adoption is underway. |
| Segway/Salesforce hybrid architecture (want #22) | — | Already decided; see Foundational Note above. Not a ranked opportunity. |
| State/regulatory registration renewal tracker (Danielle 1:1, 2026-09-XX) | 🟢 Quick Win (minor) | Small, contained tracking need (litigation-funding state registrations, annual renewals) — currently an ad hoc spreadsheet Danielle just started. Low effort, modest impact; not headline material but genuinely useful. |

---

*Source material: [[20260616-Workflow-Map-Capital-Financing-merged]] (current-state process detail), [[xx_howies_wants]] (full ranked want list with sourcing), [[xx_Project_Learnings]] (relational/behavioral context). Built from discovery through 2026-09-XX.*
