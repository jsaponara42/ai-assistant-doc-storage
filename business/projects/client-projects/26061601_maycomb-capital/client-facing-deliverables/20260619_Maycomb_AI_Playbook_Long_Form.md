---
title: "Maycomb Capital — AI Playbook (Long Form, Working Draft)"
date: 2026-06-19
tags: [client, project, deliverable-concept, governance]
ai: claude
status: needs-attention
---

# Maycomb Capital — AI Playbook (Long Form)

**A practical guide to using Claude well, experimenting safely, and sharing what works.**

*Prepared by Blue Tusk · Working draft for internal review*

> This is a draft for John-Carlos and Maycomb to react to — not the final team-facing version. Open questions and items needing Maycomb's input are marked inline with ⚠️.
>
> Companion document: a short-form cheat sheet version of this same framework, for quick day-to-day reference.

---

## What this is

You now have Claude (Team plan) available to the whole team. That's the first step done. This playbook is the short answer to the next question: *now what?*

It's written for the people who'll actually use Claude day to day — not as a rulebook to memorize, but as a guide to three things:

1. **How to experiment** without worrying you'll do something wrong.
2. **When to slow down** and double-check what Claude gives you before you rely on it.
3. **How to share** the stuff that works, so a good idea one person finds becomes something the whole team gets to use.

The whole thing fits on a few pages on purpose. If a rule here ever feels heavier than the work it's protecting, that's a bug — tell the AI owner (more on that role below) and we'll fix it.

---

## 0. The one idea underneath all of this

Maycomb Capital hires people because they're good at what they do. And yet a real share of the week probably goes to work that doesn't need much of that talent. It's necessary work. Just not the work the team is actually here for.

That's the point of bringing in AI and automation. **Not to remove the person doing the task — to remove the part of the task that wastes the person.** The hours you get back go toward the things only a person can do: judgment, relationships, the analysis that actually moves a fund forward.

So when you read the rest of this, read it as an invitation. The goal is more experimentation, not less — with just enough structure that the good ideas don't get lost and the sensitive stuff stays safe.

---

## 1. The idea & gripe list

**The single most useful habit this whole playbook asks of you: when something annoys you, write it down.**

There's one shared list — **Slack** (confirmed by Danielle as the lowest-friction home for this; anonymous posting is available in Slack but not required — Danielle noted people should put their names on items so follow-up questions can be asked). When a task irritates you, drop it on the list. That's it. Three things, thirty seconds:

- **What's the task or annoyance?**
- **Roughly how often does it happen?**
- **Roughly how long does it take?**

You do **not** have to justify it. You don't have to prove it's worth automating, explain how it'd work, or make a business case. That's deliberate — the offhand "ugh, I hate doing X every quarter" is usually the most valuable thing on the list, and making people defend their gripes is exactly how those get filtered out before anyone sees them.

**Nothing is too small or too ridiculous.** Filtering happens later, by the AI owner — not by you at the moment you're annoyed.

Two things make this list do double duty for Maycomb specifically:

- **It's also how we capture how the work actually gets done.** Every "I hate doing X" is a process worth writing down. A gripe captured today is institutional knowledge that doesn't walk out the door.
- **It's the front of the pipeline.** Everything in the rest of this playbook — the experiments, the shared SKILLS, the monthly review — starts from this list. No list, nothing to work from.

> **Norm to set explicitly:** adding a complaint here is a *valued* act, not venting. Surfacing friction is the job, not a distraction from it.

---

## 2. The question to ask before you trust an answer

Claude is genuinely good, which is exactly where the risk hides. It produces a clean, confident, plausible-looking answer every time — including the times it's wrong. The danger isn't that Claude makes mistakes; it's that a mistake can look just as polished as the truth, and get trusted and acted on before anyone checks.

So the one habit that matters most isn't about *what you put in* — it's about *how much you lean on what comes out.* Before you treat a Claude answer as fact, send it to someone, or drop it into real work, ask:

> **If this is wrong, what does it cost us? Do we lose a borrower's trust? Is there legal or financial exposure? Or is it no big deal?**

That single question sorts everything into two buckets.

### 🟢 Low stakes — use it, with a sanity-check

If a wrong answer would be easy to catch and cheap to fix, go fast and lean on Claude freely. This is most of what you'll do:

- Drafts and first cuts you're going to read and edit anyway.
- Brainstorming, summarizing, reformatting, explaining.
- Internal notes where you'd notice an error before it mattered.

Give it the obvious once-over — does this look right? — and move on. No process, no sign-off. **Most of your work lives here, and that's the point — this is where the time savings come from.**

### 🟡 High stakes — you own it, not Claude

The moment a wrong answer would actually hurt — a real credit decision, anything going to a borrower or investor, the fund's own numbers, anything that touches the firm's reputation, money, or legal standing — the rule is one sentence:

> **You are accountable for what goes out. Claude drafted it; you're signing it.**

That means a qualified person actually checks the substance — not skims it because it reads well — before it's trusted, acted on, or sent. 

Claude is a very fast assistant here, never the decision-maker. If you're not in a position to personally stand behind the output, it's not ready to leave your hands. When in doubt about whether something clears this bar, that's exactly the moment to loop in the AI owner.

**The one time to give the AI owner a heads-up first.** When you're about to use Claude for a *new* high-stakes use case — or one that's changed enough that it's effectively new — tell the AI owner before the first real run, not after. 

This is a heads-up so someone in the loop knows a sensitive workflow is starting. Then the **first run is a proof run, done together (or with the owner aware):** instead of relying on that first output, you check it against something you already know the answer to, or verify it fully by hand, to confirm the workflow actually holds up. Once it's proven that first time, it's just normal high-stakes work — own it and go, no heads-up needed each time. The trigger to repeat this is only if the use case materially changes again.

The whole gate, in 3 lines: 
*low stakes → use it and sanity-check; 
high stakes → you own it, verify before it's trusted or sent; 
new high-stakes use case → give the AI owner a heads-up and prove it once, together.*

**One separate rule, regardless of stakes:** when real Maycomb information is involved, use the **enterprise version of Claude only** — never a free or personal AI account (free ChatGPT, Claude, Gemini, etc.), since those can learn from what you type. Enterprise Claude is set up so your inputs aren't used to train the model, which is why it's safe for the real thing. (More in Section 6.)


---

## 3. When something works, make it a SKILL

This is the part that turns one person's lucky find into something the whole team owns.

Here's the failure mode we're heading off: someone figures out a genuinely great way to get Claude to draft a common document. They use it. It saves them an hour every week. And **nobody else ever finds out** — so the other eleven of you keep doing it the slow way, or worse, each invent your own slightly different version. Multiply that across every task and the team fragments into a dozen private workflows.

The fix is a simple loop: **find it → standardize it → share it.**

When you land on a Claude workflow that clearly works — a prompt, a sequence, a way of structuring a task — don't just keep using it quietly. Flag it. It gets written up once, in a consistent way, and becomes the team's standard way to do that thing. Then anyone can use it, and it gets better over time instead of being reinvented.

We'd roll this out in two phases, so it stays light now and grows only when the volume justifies it:

### Phase 1 — start this month (near-zero lift)

Live entirely inside the Claude tools you already have:

- **A shared Projects library.** When a workflow works, capture it as a Claude Project with its instructions baked in, so anyone can open it and get the same result.
- **A running "prompts that work" doc.** A plain shared list: *here's the task, here's the prompt/approach that nails it.* No formatting rules, just a growing reference.

That's enough to kill most of the "everyone reinvents the wheel" problem immediately.

### Phase 2 — the destination (when volume justifies it)

Once you've got a real stack of proven workflows and a clear sense of which ones matter, those graduate into **packaged, maintained Claude SKILLS** — reusable, versioned, invoked the same way every time, improved deliberately as the team learns. This is the difference between "a doc full of good prompts" and "a small internal library the firm runs on." It's more lift to build and keep current, which is exactly why it's Phase 2 and not a day-one requirement — you grow into it as the payoff becomes obvious.

> ⚠️ *Design note for JC: Phase 2 (maintaining a packaged SKILLS repo) is the natural paid on-ramp — it's ongoing work that doesn't fit the free roadmap scope. Mirrors how you run your own vault SKILLS.*

The graduation path across the whole playbook, in one line:

> **Gripe (§1) → try it low-stakes (§2) → it works → capture as a Phase 1 Project/prompt (§3) → if it matters, package it as a SKILL (§3, Phase 2).**

---

## 4. Which Claude to use — Haiku, Sonnet, or Opus

Inside your Claude instance you can pick which model answers you. They're named **Haiku**, **Sonnet**, and **Opus**, and they trade off speed, cost, and raw power. It's tempting to just leave it on the most powerful one all the time — but that's like taking a freight truck to pick up a coffee. Slower, more expensive, and no better at the actual errand. Matching the model to the job makes your work faster *and* keeps the firm's usage costs down.

Here's the plain-English version:

- **Sonnet — your default.** The balanced one: smart and fast, good for the large majority of what you'll do. Drafting, editing, summarizing, normal questions, working through a document. If you're not sure which to pick, pick Sonnet. Most people never need anything else.
- **Haiku — the quick one.** Fastest and lightest. Reach for it when the task is simple and you're doing a lot of it: quick lookups, sorting or tagging a list, short straightforward rewrites, anything where you want an answer instantly and the work isn't subtle. Using Haiku for the easy, high-volume stuff keeps it instant and cheap.
- **Opus — the heavy hitter.** The most capable and the most expensive to run. Save it for the genuinely hard things where the extra horsepower changes the answer: dense multi-step reasoning, untangling a complicated problem, careful analysis where being a bit sharper actually matters. Powerful, but overkill for everyday tasks — and noticeably slower and costlier, so don't leave everything parked on it out of habit.

The one-line rule:

> **Default to Sonnet. Drop to Haiku for simple, high-volume work. Step up to Opus only when the task is genuinely hard.**

A couple of practical notes:

- **This pairs with the trust check in Section 2.** A high-stakes task isn't automatically an Opus task — "how much it matters if it's wrong" (do I verify and own it?) is a separate question from "how hard is it to get right" (which model). A high-stakes but straightforward task can run on Sonnet and still get carefully checked by you.
- **You can switch mid-task.** Start in Sonnet, and if it's clearly struggling with something genuinely hard, move up to Opus for that piece. You're not locked in.

> *Design note for JC: written for the Claude.ai app picker, not the API — so no $/token tables (the team can't see those and it's not their decision surface). Guidance is relative speed/cost/capability. Current app lineup as of writing: Haiku 4.5, Sonnet 4.6, Opus 4.8. **All three models confirmed available on Maycomb's plan — corrected July 17, 2026: this is a Team plan, not Enterprise, but the model availability confirmation from the June 23–24 call still holds; Team plans separately include access to all available models by default.**_

---

## 5. Tools & access — Claude Code and Cowork

The Claude you use every day in the chat interface is a conversational tool — you ask, it answers, you decide what to do with the output. **Claude Code** and **Claude Cowork** are different in kind, not just degree. They can take actions in the real world: executing code, writing and modifying files, running commands, automating tasks directly on your machine. That's genuinely useful, but it also means a mistake isn't just a wrong answer you can ignore — it can be a change that's already happened.

For that reason, both tools are meant to be **disabled at the org level by default**, with access opened up only once a use case has been approved. **Corrected July 17, 2026: Maycomb is confirmed on a Claude Team plan, not Enterprise — the two tools aren't controlled quite the same way.**

- **Cowork** has a single organization-wide on/off switch (Organization settings → Capabilities). Barry can flip this off in a couple of clicks. The one limitation: it's all-or-nothing — there's no way to leave it on for a specific approved use case while keeping it off for everyone else. Team plans don't have the group-based / per-role restrictions that Enterprise plans do.
- **Claude Code** is included by default with every seat on a Team plan and doesn't have an equivalent simple toggle in the admin console. Turning it off (or restricting what it can do) takes a deployed managed-policy file or an MDM push — a real but heavier IT task, not a checkbox. This is worth putting in front of Barry directly, since it changes what "disabled by default" can mean in practice until that's set up.

Until Barry confirms both are actually configured this way, treat the process below as the operating norm (bring a use case first) rather than something with a technical backstop already in place for Claude Code specifically.

The process is simple:

> **Bring a specific use case to the AI owner. Once approved, the AI owner (with Barry) enables access, and you proceed.**

The AI owner isn't evaluating whether you're trustworthy; they're making sure the use case is well-scoped, that someone understands what the tool will actually do, and that there's a plan if something needs to be reversed. Once a use case is approved, it's approved — access stays on and you don't re-clear it every time. The trigger to revisit is only if the use case changes significantly.

**On Cowork specifically:** because the toggle is org-wide only on our plan, approving one use case currently means switching Cowork on for the whole team, not just the approved person — worth being upfront about when weighing whether a use case is worth it. **On Claude Code:** since there's no simple toggle, "approved" for now effectively means "the AI owner knows and has signed off," not "technically walled off for everyone else" — until Barry has a managed-policy restriction in place, this section leans more on the honor system than the Cowork process does.

What to bring to the AI owner when you have a use case:
- **What you want the tool to do** — specifically, not just "automate some stuff."
- **What it would touch** — which files, folders, systems, or processes.
- **What "undo" looks like** — what happens if it goes wrong and how you'd recover.

If you're not sure whether something counts as Claude Code or Cowork territory, a good heuristic: if it involves Claude *doing* something rather than *telling you* something, bring it to the AI owner first.

> *Design note for JC: originally written assuming Enterprise-style enforcement (global toggle + group-based restrictions). **Corrected July 17, 2026: Maycomb is on a Team plan.** Cowork still has a clean org-wide toggle (Organization settings → Capabilities), so that half of the enforcement story holds. Claude Code does not have an equivalent admin-console toggle on Team — restricting it requires a managed-settings.json policy or MDM deployment, which is a real ask of Barry's time, not a switch he flips in passing. Recommend deciding with JC whether to (a) prioritize getting Barry to actually deploy the Claude Code restriction, or (b) accept that Claude Code enforcement is process-based (AI owner approval) rather than technical for now, and say so plainly in the playbook rather than implying a technical backstop that isn't there yet. **Confirmed on the workflow deep-dive call (June 23–24):** JC recommended disabling Cowork and Claude Code by default at the org level for cybersecurity reasons; Barry affirmed. Still to confirm with Barry: who holds the admin seat, whether the Cowork toggle is actually off yet, and whether he has bandwidth for the Claude Code managed-policy work.*

---

## 6. Which tools for which data

This section is about *where* real Maycomb information is allowed to go — a separate question from the "how much do I trust the output" gate in Section 2. The core principle is short:

- **Maycomb's Claude (Team plan) is the sanctioned tool for real Maycomb information.** It's configured so your inputs aren't used to train the model — the same protection applies on Team as it would on Enterprise.
- **Free or personal AI accounts are never for real Maycomb information.** They can learn from what you type. With the Team plan subscription, the only reason you'd ever need to use a different account is image generation.
- **The output still has to clear the Section 2 bar.** Using the right tool keeps the data safe; it does *not* make the answer correct. A high-stakes output drafted in Maycomb's Claude still needs a qualified person to own it before it's trusted or sent.

> ⚠️ **NEEDS INPUT before this section can be finalized:** ~~the full tool-by-data reference (and any decision flowchart for the in-between cases) gets built once we've confirmed Maycomb's actual stack~~. **Stack now confirmed:** Claude (Team plan — corrected July 17, 2026, was previously listed as Enterprise), Excel/loan servicing model, LeverPoint (fund admin), Affinity (CRM), SharePoint, ShareFile, Slack, Teams (video only), DocuSign, Adobe, Expensify. This section can now be built out into a full tool-by-data reference matrix. *(Maycomb's Team-plan Claude is the sanctioned tool for real Maycomb information; free/personal AI accounts are never for real Maycomb data.)*

---

## 7. A 30-minute look, once a month

For the list in Section 1 to matter, someone has to actually look at it and decide what to do.

Once a month, the AI owner spends about half an hour on the gripe list: rough out the time-or-money cost of each item, sort them, and pick what's worth acting on next. Quick wins get done; bigger ones get queued or flagged for outside help; nothing just sits there silently forever.

Monthly rather than quarterly, on purpose — during the current transition things are moving fast, and a full quarter is too long to let a good idea or a painful gripe sit untouched. Once things settle, this can stretch out.

**Confirmed venue:** this review attaches to Maycomb's existing **bi-weekly Roadmap Meeting** — no new standing ritual needed.

---

## A note on who owns this — "the AI owner"

Throughout this playbook, a few jobs point to **the AI owner**: triaging the gripe list, taking the heads-up (and running the first proof run) when someone starts a new high-stakes use case, blessing a workflow as a standard SKILL, running the monthly look.

This is written as a **role, not a person**, on purpose. The expectation is that the **incoming Director of Finance & Operations inherits it** as part of that seat. That way the playbook still works the day after any one person leaves — which, given the current transition, is the entire point.

**Interim holders confirmed: Varenka Giordani** (office manager), who is already taking over the AP run and being looped into broader operations, **and Martina Sebring** (interim/fractional COO). Danielle confirmed on July 17, 2026 that with Martina now on board, the two are expected to work the AI-owner role jointly, with either able to step in if that's not how it plays out day to day. Danielle named Varenka as the original point person until the Director of Finance & Ops is hired, with a target of the new analyst being fully onboarded by August.

**A related but separate role: playbook enforcement authority.** Once this playbook is finalized, **Andi Phillips, Barry Porozni, Martina Sebring, and Varenka Giordani** will hold the authority to enforce it for the team. This is a broader group than the two-person AI-owner role above — enforcement authority is about who can require compliance with the playbook once it's live, while the AI owner is the day-to-day operator (triaging gripes, running proof runs, holding the monthly review).

---

## Start here this week

You don't have to absorb all of this at once. Three things to actually do:

1. **Add one gripe to the list.** The most annoying recurring task you can think of. That's the whole on-ramp.
2. **Try one thing with Claude.** Anything low-stakes — a draft, a summary, a question. Get a feel for it.
3. **If something works, say so.** Tell the AI owner or drop it in the "prompts that work" doc. That's how it spreads.

Everything else in here grows out of those three habits.

---

## How the pieces fit together

1. **The premise (§0)** sets the tone — this is about getting time back, not cutting jobs.
2. **The idea & gripe list (§1)** is the always-on input — nothing's too small, and it doubles as capturing how the work gets done.
3. **The trust question (§2)** is the core safety habit — low stakes, sanity-check and go; high stakes, you own the output before it's trusted or sent, and a new high-stakes use case gets a heads-up to the owner plus a proof run the first time.
4. **SKILLS (§3)** turn one person's win into the team's standard — light now (Projects + prompts doc), fuller later (packaged SKILLS).
5. **Picking the model (§4)** keeps work fast and costs down — default to Sonnet, Haiku for simple bulk, Opus for the genuinely hard.
6. **Tools & access (§5)** keeps the higher-risk tools — Claude Code and Cowork — off by default until the AI owner approves a specific use case.
7. **The data reference (§6)** keeps real-data decisions fast and consistent — to be completed once the stack is confirmed.
8. **The monthly look (§7)** is where the list actually turns into decisions.

---

## Open items (for JC / Maycomb, not the team-facing version)

1. ~~Pick the lowest-friction home for the gripe list~~ — **RESOLVED: Slack** (confirmed by Danielle).
2. ~~Confirm Maycomb's full tool stack~~ — **RESOLVED:** Claude (Team plan — corrected July 17, 2026, was previously listed as Enterprise), Excel/loan servicing model, LeverPoint, Affinity (CRM), SharePoint, ShareFile, Slack, Teams (video only), DocuSign, Adobe, Expensify. Section 6 can now be built out.
3. ~~Confirm which models Maycomb's plan surfaces~~ — **RESOLVED: Haiku, Sonnet, and Opus all confirmed available** (holds regardless of the Team/Enterprise correction).
4. ~~Confirm whether the monthly review can attach to an existing meeting~~ — **RESOLVED: bi-weekly Roadmap Meeting** (confirmed by Danielle).
5. ~~Confirm interim AI-owner arrangement~~ — **RESOLVED July 17, 2026: Varenka Giordani and Martina Sebring, working jointly**, until the Director of Finance & Ops is hired. (Originally just Varenka; Danielle confirmed the joint arrangement now that Martina is on board.)
6. Decide final altitude/voice once JC reviews — this draft leans warm and team-facing per the brief.
7. ~~Branding pass: apply Blue Tusk palette/typography when this moves from markdown to a styled HTML/PDF/slide deliverable.~~ — **DECIDED (JC, July 7): Blue Tusk branding/formatting applies.** This is a complimentary deliverable, so Blue Tusk's own visual identity is used rather than Maycomb's — no client input needed on this.
8. Confirm with Barry: who holds the Claude admin seat and what controls are currently configured. Cowork and Claude Code to be disabled by default — affirmed on call. **Updated July 17, 2026:** now that the plan is confirmed as Team (see item 9), this needs a real conversation with Barry rather than a status check — Cowork has a simple org-wide toggle he can flip, but Claude Code has no equivalent toggle on Team and would need a managed-policy/MDM deployment, which is more of his time. Section 5 has been updated to describe both paths and flag the gap; still needs JC + Barry to actually decide and execute.
9. ~~**NEEDS CONFIRMATION with Ariella (July 7 call): Which Claude plan Maycomb is actually on, and how billing works.**~~ — **RESOLVED July 17, 2026 (Danielle, by email): Team plan, not Enterprise.** This has been corrected throughout Sections 0, 4, 5, and 6 of this document, plus the Cheat Sheet and discovery brief. Practical effect: a usage allowance is bundled into the Team seat fee (unlike a usage-based Enterprise plan, which meters every token from the first one). If the team runs past their included usage, Maycomb can opt in to "usage credits" with an org-wide or per-user spend cap — so Section 2/4's "use freely, sanity-check" framing still holds without a cost caveat, though it's worth flagging to Barry/Martina that spend-cap controls exist if cost visibility becomes a concern later.
10. **Claude Fable in Section 4 (model guidance) — updated July 17, 2026 for the Team plan correction.** Fable launched June 9, 2026 as a Mythos-tier model built for long-running, complex agentic tasks, not everyday drafting or chat, and it carries premium pricing. With the plan now confirmed as Team (bundled usage allowance, not metered from the first token), the "surprise bill" risk from item 9 is softer than originally assumed — but the core recommendation is unchanged: **almost no one at Maycomb should reach for Fable by default.** Stick with Sonnet as the default, escalate to Opus for genuinely hard tasks, and treat Fable as a rare, deliberate choice for the AI owner to approve. ⚠️ Not yet confirmed whether Fable even appears in Maycomb's Team-plan model picker — worth a quick check before this makes it into the final Section 4 language, since a caveat about a model nobody can actually select is dead weight.
11. **NEW, July 17, 2026 — Playbook enforcement authority.** Andi Phillips, Barry Porozni, Martina Sebring, and Varenka Giordani were named as the people with authority to enforce the finalized playbook for the team. Added to the "AI owner" section as a related-but-separate concept. Andi Phillips is a new name with no other context yet — role/title/relationship to Maycomb unconfirmed, flagged in the discovery brief.
12. **NEW, July 17, 2026 — Varenka's email still outstanding.** Asked for directly; Danielle's reply didn't include it. Needed before Varenka can be looped into playbook distribution or the gripe-list/Roadmap-Meeting process directly.
