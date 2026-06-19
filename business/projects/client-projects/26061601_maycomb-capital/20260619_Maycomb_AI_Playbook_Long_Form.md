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

You now have Claude (the enterprise version) available to the whole team. That's the hard part done. This playbook is the short answer to the next question: *now what?*

It's written for the people who'll actually use Claude day to day — not as a rulebook to memorize, but as a guide to three things:

1. **How to experiment** without worrying you'll do something wrong.
2. **What to check** before you point Claude at real Maycomb information.
3. **How to share** the stuff that works, so a good idea one person finds becomes something the whole team gets to use.

The whole thing fits on a few pages on purpose. If a rule here ever feels heavier than the work it's protecting, that's a bug — tell the AI owner (more on that role below) and we'll fix it.

---

## 0. The one idea underneath all of this

You were hired because you're good at what you do. And yet a real share of the week probably goes to work that doesn't need much of that talent — tracking which fund a legal bill belongs to, rebuilding the same invoice every quarter, hand-checking a budget variance line by line. Necessary work. Just not the work you're actually here for.

That's the point of bringing Claude in. **Not to remove the person doing the task — to remove the part of the task that wastes the person.** The hours you get back go toward the things only a person can do: judgment, relationships, the analysis that actually moves a fund forward.

So when you read the rest of this, read it as an invitation, not a warning. The goal is more experimenting, not less — with just enough structure that the good ideas don't get lost and the sensitive stuff stays safe.

---

## 1. The idea & gripe list

**The single most useful habit this whole playbook asks of you: when something annoys you, write it down.**

There's one shared list (⚠️ *NEEDS INPUT: pick the lowest-friction home for this — a Claude Project, a shared doc, a Teams/Slack channel, whatever the team already opens without thinking*). When a task irritates you, drop it on the list. That's it. Three things, thirty seconds:

- **What's the task or annoyance?**
- **Roughly how often does it happen?**
- **Roughly how long does it take?**

You do **not** have to justify it. You don't have to prove it's worth automating, explain how it'd work, or make a business case. That's deliberate — the offhand "ugh, I hate doing X every quarter" is usually the most valuable thing on the list, and making people defend their gripes is exactly how those get filtered out before anyone sees them.

**Nothing is too small or too ridiculous.** Filtering happens later, by the AI owner — not by you at the moment you're annoyed.

Two things make this list do double duty for Maycomb specifically:

- **It's also how we capture how the work actually gets done.** Every "I hate doing X" is a process worth writing down — which matters a lot right now, with Danielle and Ariella moving on. A gripe captured today is institutional knowledge that doesn't walk out the door.
- **It's the front of the pipeline.** Everything in the rest of this playbook — the experiments, the shared SKILLS, the monthly review — starts from this list. No list, nothing to work from.

> **Norm to set explicitly:** adding a complaint here is a *valued* act, not venting. Surfacing friction is the job, not a distraction from it.

---

## 2. Two lanes for experimenting

Whether you need anyone's sign-off comes down to one question: **are you using real Maycomb information, or not?**

That's it. Two lanes.

### 🟢 Green lane — no real data. Just go.

If you're not putting any real Maycomb, borrower, fund, or investor information into Claude, you need **no permission and no process.** Go wild. This covers:

- Learning how Claude works and what it's good at.
- Public information and general questions.
- Made-up or generic examples ("draft a template quarterly investor update for a fictional fund").
- Your own writing that contains nothing Maycomb-specific.

This is where you build skill and where the best ideas get discovered — cheaply, with zero cost to "failing." The more time the team spends here, the more good workflows surface. **Most of your experimenting should live in this lane.**

### 🟡 Real-data lane — using actual Maycomb information. Check first.

The moment real Maycomb information is involved — a borrower's details, a real credit memo, the fund's actual numbers, anything headed to an investor — you're in the second lane. The rule here is simple and short:

- **Use the enterprise version of Claude only.** It's set up so your inputs aren't used to train the model. (See Section 4.)
- **Never** put real Maycomb information into a free or personal AI account (free ChatGPT, free Claude, free Gemini, etc.). Those can learn from what you type.
- **For the genuinely sensitive cases, loop in the AI owner first** — a quick check, not a formal review. "Sensitive" means things like: anything feeding a real credit decision, anything going outside the firm to a borrower or investor, or the fund's own financials. (Section 4 covers this; the full list gets finalized once we've confirmed your tools.)

That's the whole gate. Not four tiers, not a sign-off committee — just *"no real data → go"* and *"real data → use enterprise Claude, and check before the sensitive stuff."*

> ⚠️ *Design note for JC: deliberately collapsed NeighborWorks' 4 tiers + CRO sign-off into 2 lanes. At 12 people with no compliance officer, tiers are theater. The "champion fast lane" also drops as a formal thing — at this size everyone's already in the fast lane.*

---

## 3. When something works, make it a SKILL

This is the part that turns one person's lucky find into something the whole team owns.

Here's the failure mode we're heading off: someone figures out a genuinely great way to get Claude to draft the quarterly borrower invoice. They use it. It saves them an hour every quarter. And **nobody else ever finds out** — so the other eleven of you keep doing it the slow way, or worse, each invent your own slightly different version. Multiply that across every task and the team fragments into a dozen private workflows.

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

> **Gripe (§1) → experiment in the green lane (§2) → it works → capture as a Phase 1 Project/prompt (§3) → if it matters, package it as a SKILL (§3, Phase 2).**

---

## 4. Which tools for which data

The full version of this section is a simple reference: *what data is OK in which tool.* The core principle is already clear, and it's short:

- **Enterprise Claude is the sanctioned tool for real Maycomb information.** It's configured so your inputs aren't used to train the model.
- **Free or personal AI accounts are never for real Maycomb information.** They can learn from what you type. Totally fine for green-lane / no-real-data work; never for the real thing.
- **Pause and check with the AI owner when data is genuinely sensitive** — feeding a credit decision, going outside the firm, or the fund's own financials.

> ⚠️ **NEEDS INPUT before this section can be finalized:** the full tool-by-data reference (and any decision flowchart for the in-between cases) gets built once we've confirmed Maycomb's actual stack — accounting/ERP, investor portal or CRM, document management, e-signature, and any other AI tools already in use. Until then this stays at the principle level on purpose, rather than inventing a matrix around tools we haven't verified you use. *(This is the one component intentionally left minimal pending stack confirmation.)*

---

## 5. A 30-minute look, once a month

For the list in Section 1 to matter, someone has to actually look at it and decide what to do.

Once a month, the AI owner spends about half an hour on the gripe list: rough out the time-or-money cost of each item, sort them, and pick what's worth acting on next. Quick wins get done; bigger ones get queued or flagged for outside help; nothing just sits there silently forever.

Monthly rather than quarterly, on purpose — during the current transition things are moving fast, and a full quarter is too long to let a good idea or a painful gripe sit untouched. Once things settle, this can stretch out.

> ⚠️ *NEEDS INPUT: confirm whether there's an existing recurring meeting this can attach to, so it doesn't become a new standing ritual.*

---

## A note on who owns this — "the AI owner"

Throughout this playbook, a few jobs point to **the AI owner**: triaging the gripe list, the quick check before sensitive real-data work, blessing a workflow as a standard SKILL, running the monthly look.

This is written as a **role, not a person**, on purpose. The expectation is that the **incoming Director of Finance & Operations inherits it** as part of that seat. That way the playbook still works the day after any one person leaves — which, given the current transition, is the entire point.

> ⚠️ **Interim gap to close:** until the Director of Finance & Ops is hired, someone has to hold this role on a temporary basis — an internal person, Barry, or Blue Tusk on an interim basis. *(JC: this is a natural place to position the ongoing advisory retainer without baking Blue Tusk into the framework itself.)*

---

## Start here this week

You don't have to absorb all of this at once. Three things to actually do:

1. **Add one gripe to the list.** The most annoying recurring task you can think of. That's the whole on-ramp.
2. **Try one thing in the green lane.** Anything, as long as it's not real Maycomb data. Get a feel for it.
3. **If something works, say so.** Tell the AI owner or drop it in the "prompts that work" doc. That's how it spreads.

Everything else in here grows out of those three habits.

---

## How the pieces fit together

1. **The premise (§0)** sets the tone — this is about getting time back, not cutting jobs.
2. **The idea & gripe list (§1)** is the always-on input — nothing's too small, and it doubles as capturing how the work gets done.
3. **The two lanes (§2)** let you act on curiosity safely, with real friction only where real data is involved.
4. **SKILLS (§3)** turn one person's win into the team's standard — light now (Projects + prompts doc), fuller later (packaged SKILLS).
5. **The data reference (§4)** keeps real-data decisions fast and consistent — to be completed once the stack is confirmed.
6. **The monthly look (§5)** is where the list actually turns into decisions.

---

## Open items (for JC / Maycomb, not the team-facing version)

1. Pick the lowest-friction home for the gripe list (Claude Project, shared doc, Teams/Slack channel?).
2. Confirm Maycomb's full tool stack so Section 4 can be built out (accounting/ERP, CRM/investor portal, doc management, e-signature, other AI tools in use).
3. Confirm whether the monthly review can attach to an existing meeting.
4. Confirm interim AI-owner arrangement until the Director of Finance & Ops is hired.
5. Decide final altitude/voice once JC reviews — this draft leans warm and team-facing per the brief.
6. Branding pass: apply Blue Tusk palette/typography when this moves from markdown to a styled HTML/PDF/slide deliverable.
