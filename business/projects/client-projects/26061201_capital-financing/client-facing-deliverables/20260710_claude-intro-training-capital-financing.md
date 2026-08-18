---
title: "Claude Intro Training — Capital Financing Team"
date: 2026-07-10
tags: [client, project, ai, training]
ai: claude
status: ok
---

# Getting Started with Claude — Capital Financing Team

**A plain-language intro to using Claude, with examples from your actual work.**

## Summary

Howie has set the whole team up on Claude Team. This doc is a self-paced training (or live-session script) covering what Claude actually is, how to talk to it, how usage/limits work so nobody gets surprised, and a set of ready-to-paste prompts built around real Capital Financing workflows — underwriting, intake, contracting, sales follow-up, conferences, and case-expense onboarding.

## Context

Team is technologically non-savvy and new to LLMs entirely. Built for either a live walkthrough session or a standalone read-and-try document. Examples are grounded in the discovery brief and workflow map for this client (referral/intake/underwriting flow, sales accountability framework, conference lead handling, SOP drafting) rather than generic prompting examples, so the team sees their own job in it from the first line.

## Content

---

### 1. What Claude Actually Is (30 seconds, no jargon)

Claude is a chat-based assistant you talk to like a very well-read, very fast coworker. You type a request in plain English, it writes back. It's not connected to your Salesforce, Mighty, or email unless you paste information in or someone sets up a connection — **it only knows what's in the conversation**, plus general knowledge up to its training date, plus anything it looks up on the web if you ask it to.

Think of it less like a search engine and more like **a smart new hire on day one**: sharp, fast, well-spoken — but it doesn't know your file formats, your client history, or "how we do it here" unless you tell it. The more context you give it, the better the output.

**What it's genuinely good at:**
- Drafting and rewriting emails, letters, and templates
- Summarizing long documents, call notes, or transcripts
- Organizing messy information into a clean list, table, or checklist
- Explaining something back to you in plain language
- Brainstorming options when you're stuck
- Proofreading and tightening up your writing

**What it's not good at, and shouldn't be trusted for:**
- Anything requiring current, verified case-specific facts it wasn't given (it will not know a specific plaintiff's file unless you paste the details in)
- Underwriting judgment calls — Claude can help you organize the file or draft a summary, but the approve/decline decision is Christy's, not Claude's
- Anything you wouldn't want repeated back with total confidence even if it's wrong — Claude can sound sure and still be wrong, so double-check numbers, names, and dates it produces

---

### 2. A Word on Sensitive Data — Read This First

This is a financial services business handling plaintiff and law firm data — SSNs, settlement amounts, medical and legal details, bank information. A few habits to build in from day one:

- **Don't paste full SSNs, bank account/routing numbers, or full case files with plaintiff identifying detail into Claude** unless it's specifically approved for that use. For most day-to-day tasks (drafting an email, summarizing a process, writing a follow-up script) you don't need real client data at all — use a placeholder name like "Jane Doe" or "[Firm Name]."
- If you're drafting something *about* a real case, describe the situation generically ("a pre-settlement case with a clear liability finding and a $15K request") rather than pasting the actual intake packet.
- When in doubt, ask Christy or Howie whether a task needs real data or can be done with a placeholder.

This isn't about mistrust of the tool — it's the same instinct you'd already apply to any outside system.

---

### 3. How Usage Works (so nobody gets blindsided)

Claude Team gives each person their own seat with its own usage allowance — **your usage is separate from everyone else's.** If Audrey uses up her limit for the moment, it doesn't affect Brian's or Christy's — each person's included usage is their own, so one person reaching their limit doesn't slow anyone else down.

A few things worth knowing:

- **Usage resets on a rolling window, not once a day.** You get a chunk of usage, and if you use it all up, you wait for it to refresh rather than being cut off permanently. If you hit a limit mid-task, it's not a bug — it just means that window is used up.
- **Longer, more complex conversations use more of your allowance.** Pasting in a huge document, having a very long back-and-forth in one chat, or asking for a lot of back-to-back heavy analysis will burn through usage faster than short, focused requests.
- **A few habits stretch your usage further:** group related questions into one message instead of sending them one at a time, and take a moment to make sure your message is clear and complete before sending so you need fewer follow-ups. Starting a fresh chat for a new topic (instead of one giant never-ending thread) also helps.
- **If you do run out**, you're not stuck — the account Owner can turn on "usage credits," which lets people keep working past their included limit instead of getting blocked. If this happens to you regularly, flag it to whoever manages the Claude account (Howie or whoever the plan Owner is) rather than assuming you're locked out for good.

**Bottom line:** it's not unlimited, but running out isn't a dead end — it's a "wait a bit or ask for more" situation.

**How to check where you stand.** Click your initials (bottom-left corner) → **Settings** → **Usage**. You'll see two progress bars: how much of your current session you've used (Claude runs on a rolling **5-hour session window**, not a fixed daily clock), and how much of your **weekly** allowance is left, plus when each one resets. It's less "check once a day/month" and more "check whenever you're curious or about to start something big" — but that page is the one place that has the real numbers, not a guess.

---

### 4. Basic Prompting — 5 Habits That Make a Real Difference

You don't need to learn special commands or code. You're just writing clear instructions, the same way you would in a good email to a new assistant. Five habits cover 90% of it:

**1. Say what you want AND why.**
Weak: *"Write a follow-up email."*
Better: *"Write a follow-up email to a PI law firm contact who hasn't responded in 5 days about a case-expense funding request. Friendly but direct — I want to keep the relationship warm without sounding like I'm nagging."*

**2. Give it the context it needs.**
Claude doesn't know your role, your client, or your goal unless you say so. A sentence of background at the start of a chat (*"I'm a sales consultant at a pre-settlement funding company, I work with PI law firms..."*) makes every answer after that more useful.

**3. Ask for a specific format.**
If you want a table, say "put this in a table." If you want three short bullet options instead of one long paragraph, say so. Claude will guess a format if you don't specify — telling it saves a round trip.

**4. Iterate — don't expect the first draft to be final.**
Treat the first response like a first draft from a new hire: react to it. *"Good, but make it shorter and less formal."* *"I like the second option, expand on that one."* This back-and-forth is normal and expected, not a sign something went wrong.

**5. Ask Claude to ask you questions.**
This is the single most underused trick. If you're not sure what details matter, just say: **"Ask me whatever questions you need answered before you draft this."** Claude will ask for the missing pieces instead of guessing — this is especially useful for anything nuanced, like a firm onboarding script or a hard conversation with a consultant.

**6. Keep going — it's a conversation, not a vending machine.**
Once Claude hands you a good draft or answer, you don't need to start over to get the next thing done. If you're staying on the same topic, just keep talking: *"Great, now do the same thing for the case-expense version,"* or *"Good — now turn that into a checklist."* Claude remembers everything you've discussed in that chat, so each follow-up builds on what came before instead of starting from zero. Treat a good response as a step, not a finish line — the real value usually shows up two or three exchanges in, once Claude actually understands what you're after.

The flip side matters just as much: when you're moving to a genuinely different topic, start a **new chat** instead of dragging it into the same thread. A long-running conversation reprocesses everything said before it with every new message, so an old, unrelated thread quietly burns through your usage faster than a fresh one would. Rule of thumb: **same topic, keep going in the same chat. New topic, start a new one.**

---

### 5. What This Looks Like In Your Actual Job

Below are realistic scenarios pulled from how the team actually works today, matched to the role most likely to use them.

**If you're on intake/underwriting support:**
Claude can help you turn a messy intake email into a clean, organized summary before it goes to underwriting, draft a request-for-documents email to a firm that's missing paperwork, or explain an unfamiliar term in a case file in plain English. It cannot make the approve/decline call — that judgment stays with Christy.

**If you're in sales:**
Claude is strong at drafting your outreach and follow-up emails, prepping talking points before a call with a firm, and role-playing a tough conversation (like explaining case-expense terms to a firm that's never worked with you before) so you walk in prepared. It's also useful for turning a stack of conference badge scans or a rough contact list into something organized enough to hand off.

**If you're doing contracting/agreement work:**
Claude can help draft or tighten the language in a standard cover email that goes out with an agreement, build a checklist of what needs to be confirmed before an agreement is sent, or summarize a long email thread into "here's what's still outstanding."

**If you're documenting a process or writing something up :**
This is one of Claude's strongest use cases. Describe your process out loud or in rough notes, and ask Claude to turn it into a clean, structured document. This is exactly how the SOPs already being built for this project got started.

**If you're the CEO or in a leadership/coordination role:**
Claude is useful for drafting the monthly one-on-one talking points against someone's KPIs, turning a rough voice memo or meeting note into an organized recap, or thinking through a tricky people decision by asking Claude to play devil's advocate on your reasoning before you act on it.

---

### 6. Try These Prompts — Copy, Paste, Edit

Open a new Claude chat and paste any of these in, swapping the bracketed parts for your real situation. These are meant to be **starting points** — adjust freely. Most of what's below is deliberately *not* email drafting — Claude is more useful as a thought partner for organizing, prioritizing, and planning than as a fancy spell-checker, and the examples below lean into that. Organized by the two sides of the house — **Ops** (intake, underwriting, contracting, AR/payoffs) and **Business Development** (financial consultants, sales, conference/outreach).

#### Ops

**1. Clean up a messy intake submission**
```
A law firm just sent me case info for funding [paste the raw email /
notes / partial submission]. Organize this into a clean intake summary
I can hand to underwriting, and flag anything that looks missing or
unclear so I can go back to the firm for it before it holds things up.
```

**2. Build a documents-still-needed tracker**
```
Here's a list of our open case-expense files and what each one is
still waiting on [paste it in]. Organize this into a clear tracker —
what's missing, how long it's been outstanding, and which ones need
to be chased first — so I'm working from a prioritized list instead of
just whatever's on top of the pile.
```

**3. Turn a process into a written SOP — the ask-questions way**
```
I'm going to describe how I currently handle [a task — e.g. document
collection for a new intake file, or the underwriting tiering hand-off].
Ask me questions one at a time until you have enough detail, then
write it up as a clean, numbered step-by-step SOP. This is exactly how
our existing SOPs got started, so trust the process.
```

**4. Prioritize your AR follow-up list**
```
Here's a list of my open AR files with balance, days outstanding, and
any relationship notes [paste it in]. Help me decide which ones to
prioritize for follow-up this week and why, using our usual cadence
rules as a starting point — give me a short, ranked list, not just the
raw data handed back to me.
```

#### Business Development (Financial Consultants)

**1. Plan your week against your actual KPIs — the ask-questions way**
```
Howie has given me targets to hit this [week/month] — [list your real
numbers: new referrals, outreach attempts, follow-up closure rate,
pre-settlement vs. case-expense balance, whatever applies to you].
Ask me questions about where I currently stand against each one and
what's been getting in the way, then help me build a realistic plan for
this week — what to prioritize each day, how many touches I actually
need, and what I should stop letting slide.
```

**2. Triage your pipeline before you start the day**
```
Here's where my open opportunities/leads currently stand [paste a
quick list or just describe them]. Help me figure out which ones are
stalling, which need a touch today, and which are honestly worth
letting go of — I want to start the day already knowing where to spend
my time instead of guessing.
```

**3. Prep for a strategy call — the ask-questions way**
```
I have a Strategy Call coming up with a law firm that's expressed
interest in case-expense funding. Ask me whatever questions you need
about the firm, their caseload, and what they're looking for, then put
together talking points for the call and a natural way to transition
into scheduling the Onboarding Call if it goes well.
```

**4. First post-onboarding follow-up touch**
```
I just finished an onboarding call with a new law firm for case-expense
funding. They committed to sending their first referral by [date] and
named [contact] as our point person there. Draft a short, warm
follow-up email to send in the next day or two confirming what we
discussed and reconfirming that date — not a hard sell, just keeping
it top of mind.
```

---

### 7. Quick Do's and Don'ts

**Do:**
- Treat it like a conversation — you can always say "try again" or "make it shorter"
- Give real context about your role and goal
- Ask it to ask you questions when you're not sure what details matter
- Start a new chat when you're switching to a totally different topic

**Don't:**
- Paste in full SSNs, bank details, or complete real client files — use placeholders
- Assume the first draft is final — push back on it like you would a first draft from a person
- Trust specific numbers, names, or dates it produces without double-checking against the real file
- Panic if you hit a usage limit — it resets, and credits can be enabled if it becomes a regular issue

---

## Next steps

- Decide whether this is delivered as a live walkthrough session, a send-and-read document, or both.
- Confirm who the plan Owner is (for usage credit / limit questions) so the team knows who to flag to if they hit limits regularly.
- Consider a short follow-up session after 1-2 weeks of real use to collect questions and refine which example prompts actually get used.
