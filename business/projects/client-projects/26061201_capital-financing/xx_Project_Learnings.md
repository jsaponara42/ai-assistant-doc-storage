---
title: "Capital Financing — Project Learnings"
date: 2026-07-11
tags: [client, project, reflection]
ai: claude
status: ok
---

# Capital Financing — Project Learnings

Running notes on what's working and what isn't across this engagement, unstructured, no format required. Newest entries on top. This exists so the next project starts a little smarter than this one did, not to track deliverables, that lives elsewhere.

Loose prompts if it helps to get started, not a template to fill in order: What surprised you? What took longer than it should have? What would you do differently starting over? What worked better than expected?

---

### 2026-08-XX — Yasmine walkthrough call: live screen-share replaced the planned async SOP dictation

Ran a live screen-share walkthrough of JB (Mighty/Justice Bolt) with Yasmine covering the entire post-underwriting flow — Contracting, Funding, AR, and Payoffs. Result was thorough enough that the planned separate async Claude-dictation exercise for this specific workflow was dropped as unnecessary; the SOP is being built directly from this call's transcript instead. Full process detail is now in [[20260616-Workflow-Map-Capital-Financing-merged]] (W1 Steps 5–8, W2 Steps 1–7, and the new Workflow 6 section) and in the standalone SOP at `SOPs/`.

A few things worth flagging separately from the process facts themselves:

- **Concrete, first-hand data point against Segue.** Segue told Howie/the team they'd offer individual per-user FormStack-equivalent logins (vs. the current single shared group login) — but when Yasmine and the team met with them, they **could not actually demonstrate this feature working**, since it wasn't connected on Segue's end during the demo. This is real evidence for the want #5/#13 Salesforce-platform decision, not just a vague impression — worth raising directly if/when that decision comes back up with Howie.
- **Christy and Howie were both out at the time of this call**, with Howie temporarily covering underwriting himself and visibly overloaded (conference day). This is a time-bound staffing snapshot, not a structural fact — don't treat "Howie is doing underwriting" as a standing arrangement.
- **Yasmine reiterated the standing offer for a single team-wide Claude training** rather than repeating 1:1 walkthroughs — consistent with the training commitment already tracked elsewhere; no new commitment made here.
- **Confirms the earlier read on Josh** (see the 2026-08-06 entry below): Yasmine's own words were that Josh "was kind of missing that mark" on wanting this level of operational detail — he didn't want to learn this part. Corroborates the discovery brief's framing that operational depth, not just high-level SOP collection, is what actually unlocks automation scoping here.

*(open for further notes — Kaz conversation to be logged separately)*

---

### 2026-08-07 — Howie is now independently running his own Claude-generated discovery work, and named specific FC resistance (Audrey, Victoria)

Two things from the same email worth flagging together, since they're connected — both are about whether the team is actually pulling in one direction.

**Howie used Claude himself to generate SOPs/workflows for an AI engineer, and sent JC the output.** His own words: "I could do it that way... What's important is that everyone on my staff has the same tools and direction as they all can contribute." This is a coordination risk, not just a nice data point — Howie is now doing parallel discovery work outside the engaged process, using his own prompting, and it needs to be actively reconciled rather than just filed. Two things follow from this: (1) whatever he sends needs to be checked against what's already documented before it's treated as new fact, since it may duplicate, contradict, or (most likely) just be a differently-worded version of things already captured here; (2) it's a live signal for the "give everyone the same tools" want already tracked in the discovery brief/wants doc — Howie experimenting solo is exactly the kind of uneven adoption pattern the team Claude training is meant to fix.

**Howie directly questioned the FC dictation methodology and named names.** He asked whether getting workflow/SOP dictation from the financial consultants is "the direction," and whether the business is "actually measuring what they are doing" — a real methodology question, logged as an Open Question in [[xx_howies_wants]] for a direct response. He then, in the same breath, described active resistance from **Audrey and Victoria specifically**: "we are no you Howie and we need to do things our way," which he reads as them missing the distinction between copying his personal style and adopting his underlying approach to success — and he thinks that's part of why they're not succeeding. Two implications: (1) this is useful, specific context for the FC 1:1 call ([[call-prep/20260807_Capital-Financing_Financial-Consultant-Call-Prep]]) — not to raise directly (per that doc's own guidance not to lead with performance critique), but worth being alert to if it surfaces in how Audrey or Victoria describe their own process; (2) Howie's "style vs. approach" framing is his own diagnosis, not a confirmed fact — worth hearing their side before treating it as settled.

*(open for further notes)*

---

### 2026-08-06 (kickoff call with leadership team) — Promises made, team-wide Claude gap confirmed, and an informal timeline slip

Full kickoff call with Christy, Yasmine, Danielle, and Howie (Danielle joined the second half). Several things worth preserving that don't belong in the discovery brief's contractual language but matter for how the relationship is being built:

**The Claude training gap is team-wide, not just Danielle's.** Christy, Yasmine, and Danielle each independently confirmed on this call that none of them ever received the Claude training materials Howie believed had been sent. Christy: "We don't have any training documents on Claude." Danielle: used it a bit on her own, no training, found it slow — likely because she'd defaulted to a stronger, slower model than her task needed. Worth building that specific point (model selection for the task at hand) into the training content directly.

**SOPs got explicitly pinned down as fully Christy's, not a shared deliverable.** Danielle pushed hard on what the actual deliverable is, and JC confirmed clearly: the roadmap is the deliverable, SOPs are entirely Christy's own workstream on her own schedule, not part of this eight-week engagement at all (a recorded 1:1 conversation can be a useful *starting point* for an SOP as a side effect, but that's incidental, not scope). This is a tighter boundary than "not full SOP authorship" as previously logged — it's zero SOP ownership, by design.

**Christy asked for visible progress checkpoints, not a single reveal at the end.** Her own words: something "for a guide for me and Yasmin and Danielle to go, okay, we've done this, now we're working towards this." JC confirmed this is the intent. Worth actually delivering on this visibly, since it was asked for directly and on the record.

**Informal timeline slip, not yet reflected in the signed proposal.** JC's wedding/honeymoon (Aug 21 – Sept 6) overlaps with Christy and Danielle also being out the same window, plus JC being out part of the week before (Wed–Fri). Floated live as possibly making this a nine-week engagement in practice rather than eight, though nothing formal was changed. Worth tracking actual calendar time against the proposal's 8-week estimate as the engagement proceeds, and flagging to Howie directly if it's going to run past what was quoted, rather than letting it drift silently.

**SharePoint access resolved differently than previously logged.** Christy explained the SharePoint content is currently a mess — Josh had the team dump materials in with intent to clean it up later, then launched it to everyone before that happened. The team will instead send JC clean, department-ready folders directly once ready, rather than grant access to the disorganized space now. See the updated note in the discovery brief's Engagement Continuity section.

**Mighty is now "Justice Bolt" (JB).** Confirmed rebrand; both names are still used interchangeably internally. Also surfaced: no consistent unique identifier for a client/case across systems today, just names, which don't always match between Mighty/JB and Salesforce. Not something to solve now, but worth factoring into future integration/automation work.

*(open for further notes)*

---

### 2026-08-06 — Email exchange with Howie: costs, scope discipline, and a request that cuts against the proposal's design

Several threads worth preserving from this back-and-forth:

**Kaz's real cost is now known: ~$3,000/month.** Howie is cost-sensitive about paying Kaz on top of the Blue Tusk fee and directly asked whether JC could build the Salesforce automation himself instead. JC's answer: yes, can code and build in Salesforce, but full SF development is out of scope for the 8-week engagement and would need real ramp-up time on their specific instance. More efficient to keep Kaz, but manage him tightly — clear bounds, highest-impact-first, and actually turn on what he builds (directly relevant given the KPI dashboard Kaz already built has been sitting unused — see workflow map).

**The Friday meeting mystery is resolved.** It was Josh's planned recurring weekly call with financial consultants/BDRs — meant to build accountability and traction, and tied to the "shift client communications from CEO to financial consultants" note, i.e., the intended fix for what's now logged as PO-007. It never launched. See the workflow map's Consultant Authority & Client Routing section.

**Danielle never received her Claude onboarding instructions.** Howie wants training "taken to the next level." Reinforces the complimentary full-team Claude session already offered in the 2026-08-06 proposal — worth confirming Danielle specifically gets covered, since this is now the second documented adoption gap (after the team's general Claude-subscription underuse).

**Howie wants to join the first part of tomorrow's call with Christy, Yasmine, and Danielle**, framed as forecasting the proposal to them, before JC and Howie continue solo. This is a deviation from the proposal's explicit design ("individual conversations... not a group meeting") — worth watching whether the individual 1:1 resets still happen separately afterward, or whether this group framing ends up substituting for them. Not necessarily a problem, but flagging since it's a change from what was scoped and promised in writing.

**Scope discipline, stated explicitly.** JC named the Josh pattern directly to Howie in writing: not letting scope expand to the point where "it feels like nothing is getting done," concrete near-term deliverables first, widen scope later if it makes sense. Awaiting Howie's response, but worth treating this as the standing frame for the engagement regardless.

*(open for further notes)*

---

### 2026-08-06 (same day, follow-up) — Reset call with Howie: root cause confirmed, new operating model set

Spoke directly with Howie the same day Josh was let go. Key points worth preserving:

**Josh and Howie parted on good terms**, by both accounts — Howie described mutual respect and said he told Josh "I love you, man." This was a business decision, not a falling-out between the two of them personally.

**Howie's own account of root cause:** his leadership team (Christy, Danielle, Yasmine) told him directly they would not continue working with Josh — Howie called it close to a staff mutiny ("you came in with great bones and you broke everybody"). Notably, Howie says Josh focused his effort on the operations side of the business, which Howie insists had the *fewest* problems ("we don't have a lot of issues operationally... Christy and her leadership team are doing great") — while the areas Howie actually needed help with, sales and tech efficiency, went largely unaddressed. Josh's approach reportedly framed feedback as "you're the problem" rather than "here's what we could add," which landed badly with a team Howie describes as already loyal and low-turnover.

**Additional pattern evidence:** Howie says Josh told Capital Financing's own staff, directly, that he's been fired by other clients before for the same working style — wearing it "as a badge of pride" rather than treating it as a lesson. Strengthens the read from the earlier entry above: this is a recurring pattern in how Josh operates, not a one-off mismatch with this client.

**Howie self-attributes part of the gap, unprompted:** Christy holds the Director of Operations title but, in Howie's own words, was never clearly directed or delegated to lead SOP/workflow rollout — "I blame myself... I haven't told them to do that. I didn't know to do that." This is a meaningful reframe: some of what looked like operational dysfunction in the diagnostics may be a delegation gap from Howie, not a skill or effort gap in Christy, Danielle, or Yasmine.

**New operating model set directly by Howie on this call:**
- JC works primarily through Christy going forward for team dissemination — not managing the sales team or other departments directly.
- Individual 1:1 "reset" conversations planned with Christy, Danielle, and Yasmine before further work, specifically so they experience firsthand that JC's working style is different from Josh's.
- Howie wants a written proposal same day, with a call the following day to discuss.

**Secondary evidence for the tool-adoption diagnostic (PO-003/PO-004):** the team already has a Claude subscription and a training document (`client-facing-deliverables/20260710_claude-intro-training-capital-financing.md`), but per Howie it isn't being used because it feels "intimidating." Confirms that documentation alone doesn't drive adoption — worth factoring into how any new deliverable (the Opportunity Map, in particular) gets rolled out: hands-on and guided, not just handed over.

**Resulting deliverable:** see `client-facing-deliverables/20260806_proposal-capital-financing-ai-automation-mapping.md` — a tightly-scoped $5,000 / 2-month proposal built directly from this call, explicitly excluding the operational/people-management work Josh was doing.

*(open for further notes)*

---

### 2026-08-06 — Josh Henderson (partner, Ghost.Ops) fired as fractional COO by Howie

Howie fired Josh from his fractional COO role on this account. Stated reason: too hard to work with for Christy's three key operations people — Danielle (close to Howie, described elsewhere as "like family"), Christy, and Yasmine. This follows directly from the 2026-08-05 entry below (client friction that delayed sending payment links) — read together, these look like the same underlying pattern (working style causing friction with the client side) surfacing twice in quick succession, not two unrelated incidents.

**Takeaway to apply here:** treat this as a pattern, not an isolated event, when deciding how the partnership with Josh/Ghost.Ops operates going forward on client-facing roles — especially roles (like fractional COO) that require ongoing day-to-day relationship management with a client's existing staff, as opposed to project-based delivery work. Worth a direct conversation with Josh about what happened here before assigning him another client-facing operational role.

**Immediate operational impact:** JC is now the sole Ghost.Ops point of contact on this account. See the new "Engagement Continuity" section in [[20260612_discovery-brief-capital-financing]] for the offboarding handoff details (system access, vendor status, open items Josh was carrying).

*(open for further notes)*

---

### 2026-08-05 — Push for automatic/consistent payment, not a link-then-ask-later pattern

Working with Josh Henderson (partner, runs Ghost.Ops) on this account, some friction came up with the client that's delaying payment — the payment links haven't gone out yet because it would feel awkward given the difficulty. Not passing judgment on how Josh handles his own send-a-link-then-ask-for-more-later approach, but it's not the model I want for my side of things.

**Takeaway to apply here:** prefer automatic, consistent, recurring payment set up from the start over a manual link-per-cycle approach where collection depends on remembering to ask (and getting the timing/awkwardness right) each time. Consistent payment is just a better business model regardless of how a given client relationship is going.

*(open for further notes)*

---

### 2026-07-11 — Carried over from Cause Crazy: get the MSA and payment terms right before converting to a retainer

Cause Crazy started as a $4,000 project-based fee, then converted to a $2,500/month retainer once delivered. There was no proper MSA in place for that conversion, and it caused real problems: the client was constantly anxious about whether he was "earning" the retainer, even in months where delays were his fault, not mine, his card got declined after the first payment and we had to switch to direct invoicing, and payments after that were consistently late. It ended with him trying to request a refund on the last month, and that mishandling is the actual reason the relationship ended, not the work itself.

**Takeaway to apply here:** get a real MSA in place before any project-to-retainer conversion, define what "earning" a retainer means upfront, especially when delays are client-caused, and confirm a reliable payment method before the first month, not after one already fails.

*(open for further notes)*

### 2026-07-14 - Make the steps much clearer. Don't let people think.

Once you're introduced to the company, the steps should be crystal clear. People should not have to think about their part in it. In this instance, we gave people access to claude, and now everyone is trying it an asking troubleshooting questions. We need a system for that. 

Also there are many people asking about the Easy SOP process, and Howie wants much more guidance. What we will do next time is on introduction, we will set up a meeting with anyone who needs to go through the Easy SOP process and guide them through it along with how to do it in AI and what they need to send.

Ideally, they never feel the need to check in on what their role in all this is. They should be comfortable waiting for us to reach out and go about their normal days until we do. Maybe worth getting this straight with the owner so that they don't do like Howie and introduce us in a big fashion that seemingly creating a stir.

I also have to be more careful of the basic technological capability of people. Clearly I overestimated and there are many basic things that I need to dumb down to the level of. 