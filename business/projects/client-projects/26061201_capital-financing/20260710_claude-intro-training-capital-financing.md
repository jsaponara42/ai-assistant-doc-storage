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

---

### 5. What This Looks Like In Your Actual Job

Below are realistic scenarios pulled from how the team actually works today, matched to the role most likely to use them.

**If you're on intake/underwriting support (Rayna, Leifert, the doc-collection team):**
Claude can help you turn a messy intake email into a clean, organized summary before it goes to underwriting, draft a request-for-documents email to a firm that's missing paperwork, or explain an unfamiliar term in a case file in plain English. It cannot make the approve/decline call — that judgment stays with Christy.

**If you're in sales (Audrey, Brian, or anyone doing consultant follow-up):**
Claude is strong at drafting your outreach and follow-up emails, prepping talking points before a call with a firm, and role-playing a tough conversation (like explaining case-expense terms to a firm that's never worked with you before) so you walk in prepared. It's also useful for turning a stack of conference badge scans or a rough contact list into something organized enough to hand off.

**If you're doing contracting/agreement work (Yasmin's team):**
Claude can help draft or tighten the language in a standard cover email that goes out with an agreement, build a checklist of what needs to be confirmed before an agreement is sent, or summarize a long email thread into "here's what's still outstanding."

**If you're documenting a process or writing something up (anyone asked to help build out SOPs or SharePoint content):**
This is one of Claude's strongest use cases. Describe your process out loud or in rough notes, and ask Claude to turn it into a clean, structured document. This is exactly how the SOPs already being built for this project got started.

**If you're the CEO or in a leadership/coordination role:**
Claude is useful for drafting the monthly one-on-one talking points against someone's KPIs, turning a rough voice memo or meeting note into an organized recap, or thinking through a tricky people decision by asking Claude to play devil's advocate on your reasoning before you act on it.

---

### 6. Try These Prompts — Copy, Paste, Edit

Open a new Claude chat and paste any of these in, swapping the bracketed parts for your real situation. These are meant to be **starting points** — adjust freely.

**Email / follow-up drafting**
```
I'm a financial consultant at a pre-settlement funding company. Draft a
follow-up email to a law firm contact I met at a conference two weeks
ago. We talked about case-expense funding for their PI caseload. They
haven't responded to my first email. Keep it warm, brief, and low-
pressure — not salesy. Ask me any questions you need first.
```

**Summarizing something messy**
```
Here's a rough email thread / voice memo transcript / set of notes
[paste it in]. Summarize it into 3-5 clear bullet points I could hand
to a coworker who has no context, and flag anything that looks like it
still needs a decision or a follow-up.
```

**Turning a process into documentation**
```
I'm going to describe how I currently handle [a task — e.g. onboarding
a new law firm for case-expense funding]. Ask me questions one at a
time until you have enough detail, then write it up as a clean,
numbered step-by-step process document.
```

**Prepping for a hard conversation**
```
I need to have a conversation with [a coworker/consultant] about
[missed follow-up targets / inconsistent CRM logging / etc.]. Help me
think through how to open the conversation in a way that's direct but
not harsh, and role-play their likely pushback so I can practice my
response.
```

**Explaining something back in plain English**
```
Explain [a term, a clause in an agreement, a process step] to me like
I'm new to the industry — plain language, no jargon, a couple sentences.
```

**Organizing a list**
```
Here's a raw list of conference contacts [paste it in]. Clean it up,
remove obvious duplicates, and organize it into a table with name,
firm, and any notes I gave you. Flag anything where information seems
to be missing.
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
