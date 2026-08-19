---
title: Ruthless For Good — AI Playbook (Working Draft)
date: 2026-08-18
tags:
  - client
  - project
  - deliverable-concept
  - governance
ai: claude
status: ok
final-document: https://docs.google.com/document/d/15sjseki8DRw208yWzNB549-fdlZZTV6I4PUwdFLj6HQ/edit?usp=sharing
---

# Ruthless For Good — AI Playbook

**Prepared for Ruthless For Good by Blue Tusk LLC  
August 2026**

**A practical guide to using Claude well, experimenting safely, and getting comfortable turning on more powerful tools.**


> This is a draft for Martina and Aaron to react to — not the final team-facing version. Open items are marked inline with ⚠️ and collected at the end.

---

## What this is

RFG has Claude available and has been using it since April. That's the starting point. What's been missing is a shared, written answer to: *how do we use this well, and what do we need in place before we turn on the more powerful stuff — specifically Cowork?*

That's what this document is for. It covers three things:

1. **How to experiment** with Claude day to day, without worrying you'll do something wrong.
2. **When to slow down** and double-check what Claude gives you before you act on it — especially anything touching investors or deal terms.
3. **What has to be true before Cowork gets turned on** — since that's the specific thing this document is gating.

It's short on purpose. RFG is a two-person investing team; this shouldn't feel like enterprise compliance. If any rule here feels heavier than the work it's protecting, say so and it gets fixed.

---

## 0. The premise

Aaron and Michael were hired to do things AI can't do: build relationships, evaluate deals, make judgment calls. A meaningful chunk of the week currently goes to work that doesn't need that — inbox triage, CRM data entry, insurance paperwork, chasing down what was said in a conversation six months ago.

The point of bringing AI in is not to replace either of you. It's to remove the part of the job that wastes your time, so more of the week goes to fundraising conversations and deal judgment — the things that actually move Fund II forward.

---

## 1. The gripe list

**The single habit worth building: when something annoys you, write it down.**

Keep one running list in Notion —  all three of you (Aaron, Michael, and Martina) use Notion, so it's the right shared home. Martina already has a gripe list set up there, feeding into the weekly team agenda (Section 8) — this playbook builds on that existing list rather than starting a new one. When a task irritates you, add it. Three things, thirty seconds:

- What's the task or annoyance?
- Roughly how often does it happen?
- Roughly how long does it take?

No justification required. "I hate re-typing this every time I follow up with someone" is exactly the kind of thing that belongs here — don't filter yourself before someone else gets a chance to look at it.

**John-Carlos will review the list on a regular basis** — flagging anything he sees an easy or existing solution for, so items don't just sit there waiting on someone at RFG to have time to look. This is in addition to, not instead of, the weekly team check-in (Section 8).

---

## 2. Prompt modules — context you don't want to retype

A **prompt module** is a short block of background you write once and reuse — dropped into a chat or a Notion/Claude Project so you're not re-explaining the same context every time.

**Starter set for RFG:**
- **About me** (Aaron's, Michael's) — role, working style, how you like things summarized.
- **About Ruthless For Good** — the fund structure, focus areas (education, work, access), Fund I/Fund II status.
- **About our investment thesis** — what RFG looks for in a deal, what disqualifies one, the "proactive, thesis-driven" framing from the CRM work.
- **About our investors** — the kind of relationship-management context that would help Claude draft a good follow-up without you re-explaining who someone is every time.

Most of these barely change once written. A few will drift (Fund II closes, thesis sharpens) — treat that the same way a gripe gets flagged: notice it's stale, update it.


---

## 3. Picking the right model — Haiku, Sonnet, or Opus

Claude offers a few models that trade off speed, cost, and power. Matching the model to the job keeps things fast without sacrificing quality where it matters.

- **Sonnet — default.** Balanced and fast. Drafting emails, summarizing calls, most day-to-day work. If unsure, use Sonnet.
- **Haiku — quick and cheap.** Simple, high-volume stuff — quick lookups, short rewrites, tagging a list of contacts.
- **Opus — heavy hitter.** Save for genuinely hard reasoning — untangling a complex deal structure, dense multi-step analysis. Slower and pricier, so it's not the everyday default.

> **Default to Sonnet. Drop to Haiku for simple, high-volume work. Step up to Opus only when the task is genuinely hard.**

One note: how hard a task is and how much it matters if it's wrong are different questions. A high-stakes but simple task (Section 6) can still run on Sonnet — it just needs a careful human check before it goes out.

---

## 4. Tools that act — Claude Code and Cowork

This is the section that matters most right now, since it's the thing RFG named as the condition for moving forward.

The Claude you use day to day in chat is conversational — you ask, it answers, you decide what to do with it. **Cowork** (and **Claude Code**) are different in kind: they can take real actions — reading and modifying files, working across connected tools, executing multi-step tasks on your behalf. That's genuinely powerful, but a mistake here isn't just a bad answer you can ignore — it can be a change that's already happened.

For that reason: **both should stay off by default until a specific use case is scoped and approved.** The process is simple:

> **Bring a specific use case: what you want it to do, what it would touch, and what "undo" looks like. Once that's clear and approved, turn it on for that use case.**

This isn't about trust — it's about making sure someone understands exactly what the tool will do before it's live, and that there's a way back if something goes wrong.

Martina holds the Claude admin seat for RFG. Both Cowork and Claude Code are currently toggled **off** org-wide.

**Specifically for RFG:** the first real Cowork use case on the table is the inbox/calendar triage assistant for Aaron's Outlook — see the discovery brief's Action Plan. That's a good first case to run through this process deliberately, with someone checking the first output against something you already know, before trusting it to run unsupervised.

---

## 5. From win to standard — reusing what works

When something works well with Claude — a prompt, an approach, a way of drafting a follow-up — don't let it live only in your head or your own chat history. A few options, roughly in order of how often you're doing the thing:

- **Occasional:** Save it as a Notion page or Claude Project so either of you can reuse it exactly.
- **Recurring but light:** Keep a running "what works" note — task, and the approach that nailed it.
- **Doing it a third time or more:** That's the signal it's worth turning into an actual Claude **Skill** — a reusable, packaged way of doing that task the same way every time. Claude has a built-in **`/skill-creator`** skill that walks you through building one; you don't need to design the format yourself. If you're repeating something, don't hesitate to make it a skill — that's exactly what it's for.

No need to force a formal library or a review process around this — at RFG's size, the rule of thumb is simple: **twice is a coincidence, three times means build the skill.**

---

## 6. The trust gate — what to check before you rely on an answer

Claude produces confident, polished answers — including the times it's wrong. The habit that matters isn't about what you ask; it's about how much you lean on the answer before acting.

Before treating a Claude output as fact or sending it anywhere, ask:

> **If this is wrong, what does it cost us? An investor relationship? A misstated deal term? Or is it easy to catch and no big deal?**

**🟢 Low stakes — use freely, sanity-check.** Drafts you'll edit anyway, internal notes, brainstorming, first-pass summaries of a call. Give it an obvious once-over and move on.

**🟡 High stakes — you own it, not Claude.** Anything going to an investor or a portfolio company, anything stating deal terms or fund numbers, anything that becomes part of the record. A qualified person — Aaron or Michael — actually checks the substance before it goes out. Claude drafted it; you're signing it.

Given RFG's size, this mostly comes down to one practical rule: **investor-facing and deal-facing communication always gets a human read before it's sent, no matter how good the draft looks.**

---

## 7. Where data goes — which tools for which data

- **RFG's paid Claude access is the tool for real RFG information** — investor names, deal details, fund financials, anything specific to the business. RFG is on a Claude **Team plan with 3 seats** — not a free/personal account — so nothing typed into it is used to train the model.
- **Never a free or personal AI account** (free ChatGPT, free Claude, free Gemini) for real RFG data — those can learn from what you type.
- **Notion** is the primary system of record and is where most of this data already lives — same rule applies: paid/team tier only for anything real.
- **Outlook / Microsoft 365** — Claude reads Gmail natively but not Exchange directly, which is why the inbox-assistant workstream needs a specific technical approach (Claude for Outlook add-in or equivalent) rather than just pointing Claude at the inbox. This is being worked out separately.

The right tool keeps the data safe. It doesn't make the answer correct — Section 6 still applies regardless of which tool it came from.

---

## 8. The rhythm — a regular look at what's working

RFG already has a **weekly team meeting** (Aaron, Michael, Martina). Rather than create a new ritual, fold a short gripe-list check-in into that — a few minutes to see what's been added and whether anything's worth acting on. No separate monthly meeting needed at this size.

---

## 9. Who runs this

Every team this size needs one person who's the default point of contact for "is this okay to try" — not gatekeeping, just making sure someone's aware before a new high-stakes or Cowork use case goes live.

**Martina and Barry hold this role jointly** — Martina as the day-to-day point of contact, Barry weighing in specifically on tool- and permission-related questions given his cybersecurity/governance role.

---

## Appendix: Open items (for JC / RFG, not the team-facing version)

1. ~~Confirm who on the team actually uses Notion day to day.~~ **Resolved 2026-08-18:** all three (Aaron, Michael, Martina) use Notion; Martina's existing gripe list is the base for Section 1.
2. Confirm who drafts the prompt modules and on what timeline — Aaron/Michael for the personal ones, Blue Tusk can offer a first-draft skeleton for "About Ruthless For Good."
3. ~~Confirm who holds the Claude admin seat and whether Cowork is on or off.~~ **Resolved 2026-08-18:** Martina is admin; Cowork and Code both off (pending Martina's in-console confirmation once logged in).
4. ~~Confirm Twintel's tenant-permission review status.~~ **Resolved 2026-08-18:** review is complete.
5. ~~Confirm RFG's current Claude plan tier.~~ **Resolved 2026-08-18:** Team plan, 3 seats.
6. ~~Confirm who holds the "who runs this" role (Section 9).~~ **Resolved 2026-08-18:** Martina + Barry, as proposed.
7. Decide whether this stays a single working document or splits into a long-form + one-page cheat sheet (as was done for Maycomb) once RFG has reacted to this draft.
8. Branding pass: apply Blue Tusk visual identity if/when this moves from markdown into a styled deliverable, consistent with how the Maycomb version was handled.
