---
title: "Client Brief — NeighborWorks Capital"
date: 2026-06-17
tags: [client, brief, neighborworks-capital]
ai: claude
status: needs-attention
---

# NeighborWorks Capital

A national nonprofit Community Development Financial Institution (CDFI) that lends to nonprofit affordable-housing developers within a closed network. ~22 staff. Headquartered in Silver Spring, Maryland.

**Primary internal contact**
Tiana Coll — Director of Technology Operations
Phone: 240.653.6132
Email: tcoll@neighborworkscapital.org

**Secondary contact**
Rachel Haywood — Office Manager; on-site point of contact at the Silver Spring office
Email: rhaywood@neighborworkscapital.org
> ⚠️ NEEDS INPUT: Rachel's direct phone / mobile.

---

## 1. Client and Organization

- **Business name:** NeighborWorks Capital.
- **What they are:** National nonprofit CDFI; lends to a closed network of nonprofit housing developers doing affordable housing.
- **Size:** Approximately 22 employees.
- **Headquarters:** Silver Spring, Maryland (on-site office; Rachel Haywood is the on-site point of contact).
- **Decision structure for this engagement:** Tiana Coll, Rachel Haywood, and Barry Porozni are tasked by leadership with setting AI/automation direction. Final sign-off sits with the Chief Risk Officer, Beth O'Leary (Tiana's supervisor). A separate IT steering committee exists and includes the CFO, Matt Glatting.
- **CEO:** Jim Peffley.
> ⚠️ NEEDS INPUT: Main office phone and full mailing address.

---

## 2. Business Profile

NeighborWorks Capital is a mission-driven nonprofit lender — a CDFI — that provides loans to nonprofit housing developers building affordable housing. It operates as a closed network: the borrowers are a defined set of organizations, many of whom NeighborWorks Capital has lent to for as long as 20 years. Lending is at the organization level, not to individuals.

The organization is small (~22 people) and describes both itself and its broader industry as only "just starting" with AI — early-stage adoption, no entrenched tooling yet. Culturally it is risk-averse and traditional in its technology posture, which Tiana attributes to operating in the finance space where minimizing risk is paramount.

The lending pipeline is the growth engine. Tiana states this year's lending goals are large and will grow further, and frames freeing up staff capacity as a way to put more people on customer engagement and pipeline growth.

The engagement entered through "Barry," who introduced John-Carlos (owner of Blue Tusk) to Tiana and Rachel. Blue Tusk is offering a free exploratory AI/automation roadmap in exchange for learning about the industry. Current phase: pre-engagement — scoping the roadmap, pending signature of an MSA (and SOW) before deeper workflow calls begin.

---

## 3. Goals

**Personal / role goals (Tiana)**
- Be able to answer her colleagues' "why aren't we using AI?" question with specific, concrete use cases rather than generic encouragement.
- Roll out AI without becoming the person who pushed an unused tool. She won't commit to a ~$7K/year license "just to sit there."
- Maintain control of risk and data governance while still enabling experimentation.

**Business goals**
- Establish an organization-wide AI/automation vision (explicitly not limited to Tiana's own analysis/reporting function).
- Stand up a small pilot group on the paid tier of Microsoft Copilot, seeded by self-selecting "AI champions" who must ask for access and report back.
- Free up staff time spent on repetitive low-value work (e.g. credit memo production) and redirect it to customer engagement and growing the lending pipeline.
- Use AI to surface and tell the "subjective story" of borrower history and annual impact — not just the numbers already in Salesforce.

---

## 4. Key People — Internal

### Tiana Coll — Director of Technology Operations
- **Working style:** Self-describes as risk-averse; analytical (half business, half technology, but primarily analysis/reporting, not customer-facing). Wants clear, documented use cases before committing to tools. Persuadable by evidence: can secure buy-in from her risk-averse supervisor when she presents a specific use case with researched pros and cons.
- **Owns:** Technology operations; strategic IT direction (with the senior team); reporting and analysis. Functionally "the tech team" given the org's size, supported by an outside IT MSP.
- **Relevance:** Primary contact and internal champion. The person to arm with use cases and ROI framing.
- **Contact:** tcoll@neighborworkscapital.org

### Rachel Haywood — Office Manager
- **Working style:** *(inferred)* Operations-focused, hands-on with rollout and day-to-day execution.
- **Owns:** Helps roll things out; on-site point of contact at the Silver Spring office.
- **Relevance:** Conduit for on-the-ground workflow pain; supports adoption.
- **Contact:** rhaywood@neighborworkscapital.org

### Beth O'Leary — Chief Risk Officer
- **Working style:** Risk-averse but curious about new systems and products. Will give buy-in when presented with a specific use case, documented pros and cons, and evidence of research. Interested in using AI to "harvest more data from SharePoint."
- **Owns:** Final sign-off authority for this engagement. Tiana's supervisor; technology operations reports up to her.
- **Relevance:** Ultimate decision-maker / approver. Plan must be framed around expectations, ROI, and data protection to win her support.
> ⚠️ NEEDS INPUT: Beth O'Leary's contact details.

### Barry Porozni — IT strategy / cybersecurity
- **Working style:** *(inferred)* Diligent on cybersecurity (per John-Carlos's framing).
- **Owns:** Brought on ~18 months ago to help with IT strategy, tighten cybersecurity, and set the IT roadmap for the next couple of years. Part of the trio tasked with AI/automation direction. Made the introduction to Blue Tusk.
- **Relevance:** Referral source and co-owner of the AI mandate; cybersecurity gatekeeper.
> ⚠️ NEEDS INPUT: Barry Porozni's title and contact details.

### Matt Glatting — Chief Financial Officer
- **Owns:** Sits on the IT steering committee. Raised the pointed governance question of whether company data would be used to train AI models.
- **Relevance:** Governance stakeholder; a voice on cost and data-ownership risk.
> ⚠️ NEEDS INPUT: Matt Glatting's contact details.

---

## 5. Key People — External (Vendors & Partners)

### John-Carlos — Owner, Blue Tusk (the consultant; us)
- AI and automation consultant working with businesses from solo through enterprise. Offering a free exploratory AI/automation roadmap in exchange for learning the CDFI/affordable-housing-lending space.
- **Deliverable proposed:** An AI/automation roadmap — top processes prioritized by ROI (money for external-facing processes, time for internal ones), plus the overall vision. Up to three workflow deep-dive calls are within scope.
- **Method:** SOP creation via voice-note "word dump" → AI transcription → editable flow the client corrects. Documenting workflows is a built-in side benefit regardless of whether each gets automated.
- **Commercials:** Roadmap offered free. To proceed: a standard SOW for the AI/automation consultation and an MSA link (signature + confidentiality terms).

### Off-site IT Managed Service Provider (MSP)
- Provides outsourced IT support; functions as the org's IT muscle alongside Tiana.
> ⚠️ NEEDS INPUT: MSP company name and scope/terms.

---

## 6. Technology Stack

### Microsoft SharePoint
- Document repository. Holds borrower folders — credit memos and other documents accumulated over up to 20 years per borrower.
- **State:** Heavily populated but manually navigated. Summarizing borrower history today means manually opening multiple credit memos. Identified as a primary AI target (summarization).

### Salesforce
- System of record for borrower/loan data. Holds quantitative data — numbers, location.
- **State:** In use; has flow documentation. Captures the numbers but not the subjective/qualitative characteristics of borrowers and projects.

### Microsoft Copilot
- AI assistant under active evaluation. Some staff currently on the free version.
- **State:** Pilot under consideration on the paid tier (~$7,000/year per license). Preferred because it is a relatively "enclosed" system — reducing data-governance risk. Already showed promise in testing (writing use cases; potential SharePoint data harvesting).

### ChatGPT
- **State:** Requested by some staff; currently declined. Reasons: no clear use case, and unwillingness to sign over data-ownership rights to third-party software without clear understanding.

### Off-site IT MSP (infrastructure/support)
- See External Partners.

> ⚠️ NEEDS INPUT: Financial/accounting software, marketing/automation tools, and any other operationally relevant systems (not covered on the call).

---

## 7. Problem Register

### P-001 — Credit memo production is manual and time-consuming
- **Area:** Processes
- **Problem:** Producing a credit memo (reportedly up to ~30 pages) requires staff to manually pull borrower history from multiple source documents. It consumes senior people's time on assembly rather than customer engagement. Named as the top-priority "low-hanging fruit."
- **Current Thinking:** The history and inputs are scattered across SharePoint and Salesforce, so a person has to open and stitch them together each time.
- **Reframe:** The source material already exists; assembling and summarizing it is a templatable, automatable task — freeing senior staff for pipeline-growing work.
- **Approach:** Deep-dive on what a credit memo is, what goes into it, and its information sources; design an AI-assisted summarization/drafting workflow. **Status: Not started** (first workstream after MSA; Tiana to raise with Beth O'Leary at her next-day check-in).

### P-002 — No specific, usable AI use cases for staff
- **Area:** People / Processes
- **Problem:** Staff are excited by peers' AI stories from conferences but ask only "why aren't we using AI?" without concrete tasks. Tiana can't translate that into specific use cases and isn't getting traction.
- **Current Thinking:** Enthusiasm plus a tool will produce adoption.
- **Reframe:** Adoption follows specific, task-level use cases with demonstrated ROI; a self-selecting pilot of champions surfaces real ones safely.
- **Approach:** Run a pilot group on paid Copilot, access by request only; document workflows to expose concrete automation opportunities. **Status: In progress** (pilot being planned).

### P-003 — Borrower history is locked in unstructured documents
- **Area:** Systems / Tools
- **Problem:** Salesforce holds the numbers but not the subjective characteristics of borrowers and their projects. Telling a borrower's history or the org's annual impact story requires manually reading credit memos and interviewing borrowers.
- **Current Thinking:** Qualitative storytelling is inherently manual work for a dedicated case-study writer.
- **Reframe:** Much of the qualitative narrative already lives in SharePoint documents and can be summarized by AI into reusable history and impact narratives.
- **Approach:** Build AI summarization over borrower SharePoint folders for credit-memo input and broader impact storytelling. **Status: Not started.**

### P-004 — Data governance and security risk around AI
- **Area:** Systems / People
- **Problem:** Real concern that company data could train third-party models or be mishandled. Compounded by some non-tech-savvy users who might upload something they shouldn't. Mitigating factor: the org does not (and should not) collect Personally Identifiable Information (PII) in its normal course of business — lending is organization-level.
- **Current Thinking:** Risk is currently controlled by locking down access to tools while use cases are still unclear.
- **Reframe:** With defined use cases, an enclosed system, and clear data boundaries, AI can be enabled safely without signing away data rights. Rules-based automation is often the safer, deterministic answer over an LLM.
- **Approach:** Tie every recommendation to expectations, ROI, and data protection; prefer enclosed tooling (Copilot) and rules-based solutions where appropriate; respect the existing AI policy. **Status: In progress** (ongoing constraint on the whole engagement).

### P-005 — No standard operating procedures / documented workflows
- **Area:** Processes
- **Problem:** Few true SOPs exist. There are lending policies and portfolio-management policies and procedures, and Salesforce flow documentation, but not task-level SOPs. Finance is "supposed to be" working on some.
- **Current Thinking:** Existing policies are close enough; formal SOPs are overhead.
- **Reframe:** Automation requires understanding the flow; documenting 3–5 core workflows is a prerequisite and a standalone benefit even where automation doesn't follow.
- **Approach:** Use the voice-note → transcription → editable-flow method to capture 3–5 frustrating/high-interest workflows, then assess each for automation. **Status: Not started.**

> ⚠️ NEEDS INPUT: Confirm which 3–5 workflows to prioritize beyond the credit memo.

---

## 8. Action Plan

**Plan overview:** Five problems identified, clustered around Processes (manual document work) and Systems/governance (safe enablement). The principal's top stated priority — credit memo automation (P-001) — is the wedge: it is high-value, well-bounded, and draws on document sources (P-003) the team already has. The constraint cluster is data governance (P-004), which gates every tool decision. Sequencing logic: lock the agreement, document workflows before automating, prove ROI on the credit memo, then expand via the Copilot pilot — standards and governance before broad platform rollout.

### Processes

**Workstream A — Credit memo automation (P-001, P-003)**
- **Approach:** Treat the credit memo as a templatable assembly + summarization task over existing SharePoint/Salesforce sources.
- **What it involves:** Deep-dive call on credit-memo contents and sources after MSA signature; map inputs; design an AI-assisted summarization/drafting flow; attach an ROI estimate (hours saved).
- **Key Result:** A working draft-generation workflow that measurably cuts credit-memo production time and redirects senior staff to pipeline work.
- **Timeline:** First workstream post-MSA.
> ⚠️ NEEDS INPUT: Current time/cost to produce one credit memo (for the ROI baseline).

**Workstream B — Workflow documentation (P-005)**
- **Approach:** Document before automating; voice-note word-dump → transcription → editable flow.
- **What it involves:** Select 3–5 core workflows; capture each via voice note; client edits the generated flow; assess each for automation vs. rules-based handling.
- **Key Result:** 3–5 documented workflows with automation opportunities flagged.
- **Timeline:** Concurrent with early roadmap calls (up to three deep-dive calls in scope).

### People

**Workstream C — Copilot pilot & AI champions (P-002)**
- **Approach:** Self-selecting champions on paid Copilot, access by request, report-back loop.
- **What it involves:** Stand up a small pilot group; require a use case to obtain a license; gather feedback to surface real use cases.
- **Key Result:** A validated set of staff-sourced use cases and at least one demonstrated win.
- **Timeline:** Runs alongside documentation; informed by ROI framework.

### Systems

**Workstream D — Governance guardrails (P-004)**
- **Approach:** Pair every recommendation with ROI and data-protection framing; prefer enclosed and rules-based solutions; align to the existing AI policy.
- **What it involves:** Define what data may be fed to which tool; confirm enclosed-system boundaries; build approval framing for the Chief Risk Officer.
- **Key Result:** A clear, CRO-approved data-governance boundary for AI use.
- **Timeline:** Foundational; runs across all workstreams.

**Recommended sequence**
1. Sign MSA (and SOW) — gates everything.
2. Workstream D (governance guardrails) — foundational; begins immediately and runs throughout.
3. Workstream A (credit memo deep-dive) — top priority; begins right after MSA.
4. Workstream B (workflow documentation) — concurrent with A; feeds automation backlog.
5. Workstream C (Copilot pilot) — runs alongside, validated against ROI and governance.
6. Roadmap deliverable — ROI-prioritized process map + overall vision, built from A–C.

---

## 9. Engagement Metrics

Baseline scorecard — first brief, mostly ungraded.

- **Comprehension** — Ungraded (baseline). Client grasps the pilot/champion approach; appears aligned.
- **Adherence** — Ungraded (baseline). Pending signed MSA.
- **Adoption** — Ungraded (baseline). No tooling rolled out yet beyond free Copilot.
- **Velocity** — Ungraded (baseline). Gated by sign-off cadence and the Chief Risk Officer's approvals; expect a deliberate, risk-managed pace.
- **Volume** — Low (baseline). One priority workflow (credit memo) plus 3–5 workflows to document.

**Live watch-point:** Data-governance approval is the rate-limiter. Velocity will track how efficiently use cases are documented and presented to Beth O'Leary.

---

## 10. Recommended Service Tier

> ⚠️ NEEDS INPUT: Confirm against Blue Tusk's defined service tiers / pricing.

The diagnostic roadmap itself is being delivered free as an exploratory engagement. Based on five active problems, multiple concurrent workstreams (documentation + pilot + governance), and meaningful coordination load across internal stakeholders (Chief Risk Officer, CFO, Barry Porozni, the IT MSP), this points toward a structured ongoing engagement after the roadmap — to run the credit-memo build, manage the pilot, and shepherd governance approvals — rather than a one-off project. *(inferred — confirm tier and price range.)*

---

## 11. Upsell Opportunities

Paid work that can grow out of the free roadmap. Each lists the trigger — the signal that says it's time to raise it. The governing rule for this client: never lead with the upsell. Beth O'Leary (Chief Risk Officer) and Matt Glatting (CFO) approve spend on documented use case + ROI, so every upsell lands only after a prior win has been proven and quantified. Sequence beats ambition here.

### U-001 — Build & implement the credit-memo automation
- **What:** Move P-001 from roadmap recommendation to a built, deployed workflow (the org's own stated top priority and "low-hanging fruit").
- **Approach when raising:** Lead with the ROI baseline (hours per memo × memos per year). Frame as freeing senior staff for pipeline growth, which is their stated business goal.
- **When to approach:** Right after the roadmap is delivered and the credit-memo deep-dive has produced a time/cost baseline. This is the natural first paid engagement — don't dilute it by bundling others.

### U-002 — Borrower-history & impact-storytelling summarization
- **What:** Build the SharePoint-summarization workflow (P-003) — auto-summarize borrower folders for credit memos and for the annual impact/case-study narrative.
- **Approach when raising:** Tie directly to Beth O'Leary's stated interest in "harvesting more data from SharePoint." She is already pulling in this direction — present it as her idea realized.
- **When to approach:** Immediately after U-001 proves the summarization pattern works and is safe. Riding a delivered win lowers the governance bar.

### U-003 — Workflow documentation as a standalone service
- **What:** Productize the voice-note → SOP method (P-005) across the 3–5 core workflows, and beyond.
- **Approach when raising:** Sell the byproduct as the product — they admitted SOPs barely exist and finance "is supposed to be" writing them. Position as low-risk, immediately useful regardless of automation.
- **When to approach:** Early — this is the lowest-risk paid item and can run concurrent with U-001. Good "land" offer if a full build feels too big a first commitment.

### U-004 — Copilot pilot management & AI-champion enablement
- **What:** Run the pilot (P-002) as a managed service — onboarding, use-case capture, training the champions, reporting results to leadership.
- **Approach when raising:** Frame around their fear of paying ~$7K/license for shelfware. You de-risk the spend by driving adoption and proving usage.
- **When to approach:** Once the pilot group is named and licenses are being considered. Pairs naturally with U-003 (documentation feeds the pilot's use cases).

### U-005 — Governance & AI-policy framework
- **What:** Formalize the data-governance guardrails (P-004) — what data goes to which tool, enclosed-system boundaries, an operational layer under their existing AI policy.
- **Approach when raising:** Speak directly to the CFO's model-training concern and Tiana's risk aversion. Position as the precondition that unlocks everything else safely.
- **When to approach:** Can be raised early as an enabler, but easiest to sell once a concrete tool decision (Copilot paid tier) forces the question. Let the need surface it rather than pushing.

### U-006 — Retained ongoing engagement
- **What:** Convert from project work to a standing retainer covering build, pilot, governance, and new-workflow automation as the lending pipeline scales.
- **Approach when raising:** Anchor to their own words — lending goals are "huge and will get bigger." A retainer is how the automation keeps pace with growth instead of being a one-time fix.
- **When to approach:** After at least one paid project (ideally U-001) has delivered measurable ROI and trust is established. This is the last upsell, not the first.

> ⚠️ NEEDS INPUT: Map each upsell to a Blue Tusk price point / tier.

---

## Open questions (NEEDS INPUT, collected)

1. Rachel Haywood's direct phone/mobile. *(Tiana: 240.653.6132 — confirmed.)*
2. Main office phone and full Silver Spring mailing address.
3. Barry Porozni's title and contact details.
4. Matt Glatting's (CFO) contact details.
5. Beth O'Leary's (Chief Risk Officer) contact details.
6. Name and scope/terms of the off-site IT MSP. *(Owner: Barry Porozni — scope still unknown.)*
7. Full technology stack beyond Salesforce (financial/accounting, marketing/automation, and other systems — more expected).
8. Current time/cost to produce one credit memo (for the ROI baseline).
9. Confirm the recommended service tier and map each upsell (U-001–U-006) to a Blue Tusk price point.

*Resolved this round: CEO (Jim Peffley), Barry's full name (Barry Porozni), CFO identity (Matt Glatting), Tiana's phone, priority workflows (current set fine for now).*
