---
name: ai-roadmap-call-prep
description: "Generates a Call Brief that prepares JC to run a Free AI Roadmap Consultation intro/sales call for Blue Tusk. Produces a workflow hypothesis map (back office vs. value drivers), a Hormozi-style pain discovery question flow, tailored objection handling, and a close that points to the right Blue Tusk offer. Use any time JC provides a company name, website, and the person(s) he's meeting — regardless of industry. Triggers on 'prep me for a call with', 'call brief for', 'I have a meeting with', 'sales call prep', 'discovery call prep', 'intro call with', 'build my prep doc for', 'I'm meeting with [name] at [company]', or any time company + website + attendee(s) are given together. If any required input is missing, ask before proceeding. Always use before an AI Roadmap consultation call, even if JC doesn't say 'skill'."
---

# AI Roadmap Call Prep

Prepares JC to walk into an intro call confident: knowing how the prospect's business probably runs, where it probably hurts, what they'd probably love to supercharge, and exactly which questions will let *them* conclude that working with Blue Tusk is the way out.

---

## What Blue Tusk actually sells (read this first)

Every section of the brief should point toward this. Blue Tusk is not a tool vendor or an automation dev shop. The core promise:

> **We ground your team and give you confidence in the next steps of AI and automation, built around how your business actually works.**

The deliverable the call leads to is an **AI & Automation Roadmap / Opportunity Map** (see `business/projects/client-projects/26061201_capital-financing/client-facing-deliverables/20260910_capital-financing-opportunity-map-final.md` and `business/projects/client-projects/26061601_maycomb-capital/client-facing-deliverables/20260707_Maycomb_Capital_AI_Roadmap_Client.md`). It:

- Documents how the back office actually runs, often for the first time
- Maps the value drivers (revenue, growth, mission), which most firms never look at
- Ranks every opportunity by effort and impact: 🟢 Quick Win, 🔵 Near-Term, 🟣 Strategic, ⚪ Needs Decision First
- Gives the team one list to check new ideas against, so priority stops getting re-litigated
- Addresses adoption and governance, because AI access alone doesn't create consistent use

Core philosophy to echo on calls: **AI shouldn't replace judgment. It should stop wasting judgment on work that doesn't need it.**

### Offer ladder (for the close)

| Step | What it is | When it fits |
|---|---|---|
| Free AI Roadmap Consultation | This call | Always the entry |
| AI & Automation Opportunity Map | ~6–8 week fixed-fee discovery + ranked roadmap (reference: $5K fixed fee on a past engagement; JC sets pricing) | Default next step for most qualified prospects |
| Document/file organization audit | Small, bounded, fast | Prospect is hesitant, budget-tight, or heavy on AI inside their files |
| Claude/AI team training | Live session + quick-reference guide | They've bought AI seats but usage is fragmented |
| Quick-win builds | Scoped individually | After a map exists, or one obvious win is already clear |
| Ongoing AI steward | Monitoring, training for new hires, decision support | Post-map, or teams mid-transition with no real AI owner |

---

## Required Inputs

Confirm all three before any research:

1. **Company name**
2. **Company website**
3. **People attending**: name(s) and title(s)

Optional but useful: how the lead came in (referral, cold email, inbound), anything they already said about why they're taking the call, call date.

If anything required is missing:

> "To prep the brief I need the company name, their website, and who you're meeting with (name + title). What's missing? And if you know how they came in or what they said they want, that helps too."

---

## Research Process

Run all five stages before writing. **Tools are signals, not the point.** JC doesn't need a tech stack inventory. He needs to know which workflows exist, which ones are annoying, and which ones make money.

### Stage 1 — How the business makes money

**Goal:** Trace the revenue path end to end. Everything else hangs off this.

1. `web_fetch` the homepage, About, Services/Products, Team, and Careers pages (if present).
2. Web search: `[Company] LinkedIn`, `[Company] reviews`, `[Company] news`, `[Company] hiring`.
3. Answer in plain words:
   - **Who pays them, for what, and how often?** (one-time project, recurring retainer, transaction fee, AUM, etc.)
   - **Where do customers come from?** (referrals, partners, ads, conferences, outbound, repeat business)
   - **What happens between "new lead" and "paid"?** Sketch the path: source → intake → sale/qualify → deliver → bill/collect → retain/refer.
   - **Size and stage:** headcount tier (solo / 2–5 / 6–15 / 16–50 / 50+) and growth/established/mature.
4. Watch for **why-now signals**:
   - Leadership changes, new hires in ops/finance, people leaving (knowledge walking out the door)
   - Heavy admin/ops hiring (manual process overload)
   - Active ad spend, conference circuit, new locations or products (lead flow outpacing follow-up)
   - Reviews mentioning slow response, "had to follow up," disorganization
   - Any sign they've bought AI (Claude, ChatGPT Team, Copilot) or announced an "AI initiative"

### Stage 2 — The people on the call

For **each attendee**:

1. Web search `[Name] [Company] LinkedIn` and check their bio page. Capture title, tenure, prior background, and any public posts/interviews.
2. Classify their **frame**, which changes how JC runs the call:
   - **Founder/CEO:** cares about growth, their own time, not being the bottleneck. Often blind to their own bottlenecks. Talk outcomes, not process.
   - **Operator (COO/DOO/Ops Manager):** lives in the back-office pain daily. Cares about sanity, team capacity, not being the only one who knows how things work. Talk specifics.
   - **Finance lead:** cares about accuracy, close cycle, reconciliation, dependency on one person's memory.
   - **Sales/BD lead:** cares about pipeline visibility, follow-up consistency, conversion.
   - **New leader (<18 months):** actively hunting problems, wants early visible wins. Change-ready.
   - **Long-tenured leader:** needs reframing, not convincing. Ask questions that let them see it.
3. Note **their likely personal win**: what would make *this person* look good or feel relief? This is often different from the company's win.
4. Note who is **not** on the call who probably decides (CEO, partners, board). Flag it.

### Stage 3 — Workflow Hypothesis Map (the core of the brief)

**Goal:** Before the call, hypothesize the workflows this business runs, split into two buckets, and for each one guess what's annoying today and what "supercharged" would look like.

**Back office (cost centers):** work that has to happen but doesn't grow the business. Typical candidates:
- Billing, invoicing, AP/AR, collections, reconciliation, month/quarter close, budget-to-actuals
- Intake paperwork, document collection, data re-entry between systems
- Compliance, regulatory filings, renewals, reporting obligations
- Scheduling, internal status updates, "where is this at?" check-in emails
- HR/onboarding, internal FAQs, SOPs that live in one person's head
- File/document organization, shared drives nobody trusts
- Leadership inbox triage (leaders drowning in email that shouldn't reach them)

**Value drivers (revenue, growth, mission):** work that, done better or faster, makes more money or more impact. Typical candidates:
- Lead sourcing, referral partner relationships, conferences, outbound
- Sales follow-up, pipeline movement, proposal/quote turnaround
- Client/customer delivery quality and speed
- Client communication and experience during delivery
- Retention, reactivation, upsell, referral asks
- Investor/stakeholder relations, fundraising, outcome/impact reporting
- Expert judgment work (underwriting, diagnosis, strategy) that's being diluted by admin

For this specific company, produce **4–6 back-office workflows** and **3–5 value drivers**. For each:
- **Workflow:** named in their industry's language, not generic
- **Likely daily annoyance:** concrete. Not "communication issues" but "someone emails every open client weekly asking for status, by hand, and the cadence depends on who remembers."
- **Supercharged version:** what it looks like if this worked beautifully (the "vacation")
- **Probe question:** one natural question to confirm or kill the hypothesis
- **Confidence:** High / Medium / Low, based on evidence vs. industry inference

Use industry knowledge for the base layer; web search if the industry is niche. Ask: what's still manual at "modern" firms this size, where does client communication break, what documentation burden is inherent, where does revenue leak from process gaps (not strategy gaps), and what breaks at the next size tier?

### Stage 4 — Pattern match against past engagements

Check the prospect against patterns seen in real Blue Tusk engagements. Each match becomes a hypothesis to probe and an anonymized proof story JC can tell.

| Pattern | What it looked like | Proof story JC can use |
|---|---|---|
| **Knowledge walking out the door** | Key finance/ops people leaving; processes lived in their heads | "One client had two people leaving who were the only ones who knew how the AP run worked. Documenting that first was worth something on its own." |
| **Already built, never adopted** | CRM pipeline stages, automated tasks, and a KPI dashboard all built and unused | "A lending client had the entire sales follow-up system already built in their CRM. Nobody used it. The biggest win wasn't a build, it was adoption." |
| **AI bought, usage fragmenting** | Claude rolled out to the whole team; a few people great, most not | "Access alone doesn't create consistent use. A few people get good at it, most don't, and the gap grows." |
| **Leader as the bottleneck** | CEO handling 200–300 emails/day; every case routed to one person for review regardless of whether it needed their judgment | "Their operations director reviewed every single case, even ones that clearly failed basic rules. Structuring the rules layer freed her for the calls only she could make." |
| **Growth capped by follow-up, not lead flow** | Plenty of referrals; inconsistent follow-up; no visibility into who's working what | "Growth wasn't capped by leads coming in. It was capped by what happened after a lead landed." |
| **Double work between systems** | Same invoice tracked internally and by an outside administrator, then reconciled against itself | "They were tracking every invoice twice and reconciling it against itself every two weeks." |
| **Files nobody trusts** | No folder structure, sensitive docs moving by email attachment | "As AI starts working inside your files, how they're organized decides whether you get the right answer or a confident wrong one." |
| **Outsourced with no visibility** | Vendor (SEO, bookkeeping, IT) sends reports nobody can evaluate | "They'd outsourced SEO for years and had no independent way to tell if it was working." |

Flag the 2–4 patterns most likely for this prospect.

### Stage 5 — Build the sales conversation

Now turn the research into a call JC can run. Principles (Hormozi-style):

- **They say the problem, not JC.** People believe what they conclude. JC's job is to ask until they name it, then label it back in their words.
- **Pain before solution.** Don't pitch the roadmap until they've named a problem, felt its cost, and described what better looks like.
- **Make the gap concrete.** Current state vs. desired state, in hours, dollars, people, or missed opportunities.
- **Have them argue for change.** "On a scale of 1–10, how important is fixing this? … Why not lower?" makes them state their own reasons.
- **Sell the vacation, not the plane ride.** Describe the destination (a team that knows what to do next, a leader who isn't the bottleneck, judgment spent on judgment work), not the process (8 weeks of working sessions).
- **Stay honest.** JC's brand is candor: "no promises," "what this isn't," "that's not my background." Never manufacture urgency. If it's not a fit, say so. That candor is itself a closing asset.

Build the call flow using the **CLOSER** structure, adapted for a ~30-minute intro call:

1. **C — Clarify why they're here (2–3 min).** Why this call, why now.
2. **L — Label the problem (after discovery).** Restate their pain in their words; get a "yes, exactly."
3. **O — Overview past attempts (5 min).** What they've tried, what happened, why it didn't stick.
4. **S — Sell the vacation (3–5 min).** Have them describe the future state; JC connects it to the roadmap.
5. **E — Explain away concerns (5 min).** Objection handling.
6. **R — Reinforce the decision (2 min).** Confirm next step, recap in their words.

The heavy lifting (10–12 min) is **pain discovery** between C and L. Use the Pain Ladder:

| Rung | Purpose | Stock question (tailor each one) |
|---|---|---|
| Current state | Get the picture | "Walk me through what happens from when a [lead/case/client] comes in to when you get paid." |
| Problem | Find the friction | "Where in that does it slow down or depend on someone remembering?" |
| Cost | Quantify | "Roughly how many hours a week does that eat? Whose hours?" |
| Consequence | Make it real | "What's happened when that slipped? Lost a client? A late close? A deal that went cold?" |
| Why not solved | Surface blockers | "What's stopped you from fixing it so far?" |
| Future state | Build the vacation | "If that worked the way you wanted six months from now, what would be different for you personally?" |
| Priority | Make them argue for it | "1–10, how important is fixing this this year? … Why not a [lower number]?" |
| Commitment | Test readiness | "If there were a clear plan, who'd need to be involved to act on it?" |

**Always include these backbone questions (adapt wording to the person):**
- "What made now the right time to take this call?"
- "What's taking the most time in your operation right now that you wish wasn't?"
- "If your business doubled tomorrow, what breaks first? Who would you have to hire first?"
- "Where does your team's best judgment get spent on work that doesn't need it?"
- "If you could supercharge one part of the business, the part that actually makes money, what would it be?"
- "How is your team using AI today, honestly? Who's good at it and who isn't?"
- "What have you already tried? What happened?"
- "What happens if nothing changes over the next 12 months?"

Then write **tailored questions for every workflow hypothesis** from Stage 3, plus person-specific questions from Stage 2.

### Objection handling

Pick the **5–7 objections most likely for this prospect** (frame, stage, why-now signals). For each, write: what they'll say, what's usually underneath it, JC's response, and a question that hands the decision back to them. Hormozi's rule: objections are about circumstances (time, money, fit), other people (partner, board), or self (fear of wasting money, of change). Answer the real one, then return to their stated pain.

Starter library (tailor the responses using this prospect's research):

| Objection | Usually underneath | Response angle | Hand-back question |
|---|---|---|---|
| "We already have Claude/ChatGPT/Copilot. The team can figure it out." | Tool = solution belief | Access isn't adoption. A few people get good, most don't, the gap grows. The question isn't the tool, it's where to point it. | "How consistent is usage across the team today? Who'd you say is getting real value?" |
| "We have someone internal for this (IT / admin / ops)." | Loyalty, or fear of redundancy | The map makes that person more effective. It's their onboarding doc and priority list, not a replacement. On past work, the internal admin was one of the biggest beneficiaries. | "Does that person have time to step back and map the whole business, or are they buried in requests?" |
| "Not the right time. We're mid-transition / too busy." | Overwhelm | Transition is exactly when it matters: knowledge is leaving, new people are arriving, and every new hire resets adoption. The cheapest time to document is before the people who know leave. | "What's the cost if the people who know how [X] works leave before it's written down?" |
| "Just build it. We don't need a report." | Past consultants delivered shelfware | Automating before mapping means automating the wrong thing. The map is built to be used without JC in the room, and quick wins get flagged as they surface. | "Of the things you'd want built, how confident are you that's where the highest ROI is?" |
| "What do we actually get?" | Burned before | Show the shape: documented workflows, ranked opportunities, quick wins, one list for all future ideas. | "If you had a ranked list like that today, what would you do first with it?" |
| "It's too expensive / no budget right now." | Value not yet felt, or real constraint | Tie back to the cost they named on this call. If genuinely tight, offer the smaller entry (file audit or training). | "Earlier you said [pain] costs roughly [X]. How does that compare?" |
| "I need to talk to my partner / CEO / board." | Other people, or a soft no | Offer to help them sell it internally: a one-page summary, or a short call with the decision-maker. | "What do you think they'll push back on? Let's work through it now." |
| "Our work is too relationship/judgment-driven for AI." | Fear of dehumanizing the business | Agree. AI shouldn't replace judgment. It should stop wasting it on data entry, lookups, and chasing status. | "How much of your best people's week goes to work that isn't judgment?" |
| "We tried something before and it didn't stick." | Adoption burn | That's the most common failure, and it's usually adoption, not the tool. Adoption and governance are built into the roadmap. | "Why do you think it didn't stick?" |
| "Send me something and I'll think about it." | Unaddressed concern | Honest check-in, no pressure. | "Happy to. Usually that means something's not sitting right. What's the part you're unsure about?" |

### Close

Write a short, tailored close script:
1. **Label:** "So if I'm hearing you right, the real issue is [their words], and it's costing you [their number]. Fair?"
2. **Bridge:** "The way I usually tackle that is [one sentence on the roadmap, framed around their pain]."
3. **Let them decide:** "Does that sound like what you need, or am I off?"
4. **Next step:** the right rung of the offer ladder for this prospect, plus what JC sends after the call.

---

## Call Brief Format

```
# Call Brief — [Company Name]
**Call date:** [if known]  |  **Industry:** [industry]  |  **Lead source:** [if known]

## 30-Second Snapshot
[3–4 sentences: what they do, how they make money, size/stage, and the single most likely reason they'd need Blue Tusk right now.]

## Why Now
- [Why-now signal + source]
- [Why-now signal + source]

## The People
### [Name] — [Title]
- **Frame:** [founder / operator / finance / sales / new leader / long-tenured]
- **Tenure & background:** [1 line]
- **Their personal win:** [what makes this person look good or feel relief]
- **How to talk to them:** [1 line: outcomes vs. specifics, pace, what to mirror]
- **Notable:** [public content, phrases they use]

**Decision-maker on the call?** [Yes / No — who else decides]

## Workflow Hypothesis Map

### Back Office (cost centers)
| Workflow | Likely daily annoyance | Supercharged version | Probe question | Confidence |
|---|---|---|---|---|

### Value Drivers (revenue / growth / mission)
| Workflow | Likely daily annoyance | Supercharged version | Probe question | Confidence |
|---|---|---|---|---|

## Patterns to Probe (from past engagements)
1. **[Pattern]** — [why it likely fits] — *Proof story:* "[anonymized story]"
2. ...

## Call Flow (≈30 min)
**C — Clarify (0–3):** [2 tailored opening questions]
**Pain Discovery (3–15):** [Pain Ladder questions tailored to the top 2–3 hypotheses]
**L — Label:** "So the real issue is ___, and it's costing you ___. Fair?"
**O — Past attempts (15–20):** [2 tailored questions]
**S — Sell the vacation (20–24):** [future-state questions + 1–2 lines connecting to the roadmap]
**E — Concerns (24–28):** see Objection Handling
**R — Reinforce & next step (28–30):** [close script + proposed next step]

## Question Bank
**Backbone:** [the 8 backbone questions, adapted]
**Workflow-specific:** [1–2 per hypothesis]
**Person-specific:** [1–2 per attendee]

## Objection Handling (most likely for this prospect)
| They say | Underneath | Response | Hand-back question |
|---|---|---|---|

## Recommended Next Step
**Offer:** [rung of the offer ladder] — **Why:** [1 line]
**Fallback if hesitant:** [smaller entry]
**Send after the call:** [recap email, sample map excerpt, etc.]

## What to Listen For
[2–3 concrete green-light signals, e.g., they quantify a cost unprompted, they name a person leaving, they ask "how would that work for us"]

## Red Flags
[Mismatch signals: wants a tool vendor, no decision-maker, no real pain, wants free implementation, too small. Or "None identified."]
```

---

## Widget

Render the brief with `show_widget` (call `read_me` first, silently) so JC can scan it before the call:

- Outer card: `border: 0.5px solid var(--color-border-tertiary)`, `border-radius: var(--border-radius-lg)`, padding 1.5rem
- Section headers: 13px, 600 weight, uppercase, 0.05em letter-spacing, `var(--color-text-tertiary)`
- 30-Second Snapshot: slightly larger body text at top, no border
- Workflow Hypothesis Map: two tables side by side on desktop (stacked on mobile). Back Office header with grey accent, Value Drivers header with blue accent (`#378ADD`). Confidence shown as a small pill.
- Call Flow: collapsible `<details>` per stage, so the whole call fits on one screen collapsed
- Questions: light background block (`var(--color-bg-secondary)`, 4px radius, 6px 10px padding, italic)
- Objection Handling: `<details>` per objection; summary = what they say, body = underneath / response / hand-back
- What to Listen For: green left border `#2E9E6B`; Red Flags: orange left border `#E07B3A` (grey if none)
- "Copy as Markdown" button at the bottom that copies the full brief
- CSS variables for all colors except the accent borders above

---

## Output File

After rendering, save the brief to the vault (use the vault-mcp skill conventions):

```
business/projects/internal/sales-call-prep/YYYYMMDD_call-brief-[company-slug].md
```

Include vault frontmatter (`title`, `date`, `tags: [client, strategy]`, `ai: claude`, `status: ok`). Confirm the saved path to JC.

---

## Quality Check (run before rendering)

- [ ] All three required inputs confirmed before research
- [ ] Website fetched, not just searched
- [ ] Revenue path traced: source → intake → sale → deliver → bill → retain
- [ ] 4–6 back-office and 3–5 value-driver workflows, named in the industry's language
- [ ] Every workflow has a concrete annoyance, a supercharged version, a probe question, and a confidence level
- [ ] Tools mentioned only as signals, not as the substance
- [ ] 2–4 past-engagement patterns flagged, each with an anonymized proof story
- [ ] Call flow questions are tailored, not just the stock versions
- [ ] Pain Ladder includes cost, consequence, and a "why not lower?" priority question
- [ ] 5–7 objections chosen for this specific prospect, each with a hand-back question
- [ ] Recommended next step names a specific rung of the offer ladder, plus a fallback
- [ ] Decision-maker status flagged
- [ ] No manufactured urgency; responses fit JC's candid voice
- [ ] Widget rendered with Copy as Markdown; file saved and path confirmed
