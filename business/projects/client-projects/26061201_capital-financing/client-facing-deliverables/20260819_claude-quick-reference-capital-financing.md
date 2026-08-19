---
title: "Claude Quick Reference — Capital Financing Team"
date: 2026-08-19
tags: [client, project, ai, training]
ai: claude
status: ok
---

# Claude Quick Reference — Capital Financing Team

**A scannable reference, not a read-once training doc. Come back to it when you need it.**

## Summary

Condensed version of the full Claude training doc. Same content, built for lookup instead of one-time reading. See [[20260710_claude-intro-training-capital-financing]] for the full walkthrough with explanations.

## Content

---

### 1. What Claude Is

A chat assistant. Type a request in plain English, it writes back. It only knows what's in the conversation, plus general knowledge, plus anything you ask it to look up.

Treat it like a smart new hire on day one: sharp, but it knows nothing about your files, your clients, or "how we do it here" unless you tell it.

| Good for | Not good for |
|---|---|
| Drafting and rewriting emails, letters, templates | Case-specific facts it wasn't given |
| Summarizing documents, call notes, transcripts | Underwriting decisions — that judgment stays with Christy |
| Organizing messy info into a list, table, checklist | Anything you'd repeat without double-checking — verify names, numbers, dates |
| Explaining something in plain language | |
| Brainstorming options | |
| Proofreading | |

**Watch for:** Claude is tuned to agree with you. Ask directly for pushback: *"Be critical of this,"* or *"Tell me what's wrong with this before what's right."*

---

### 2. Sensitive Data Rules

- Do not paste full SSNs, bank/routing numbers, or full case files with plaintiff-identifying detail.
- Use placeholders for day-to-day tasks: "Jane Doe," "[Firm Name]."
- Describe real cases generically ("a pre-settlement case with clear liability, $15K request") instead of pasting the intake packet.
- Unsure if something needs real data? Ask Christy or Howie.

---

### 3. Why the Team Plan

| Reason | What it means |
|---|---|
| Shared Skills | One person solves a task, the whole team gets it |
| Centralized Connectors | Set up once (e.g. SharePoint), works for everyone |
| Data security | Confidential plaintiff/firm data needs the paid plan's protections, not a free personal account |

---

### 4. Usage

| Question | Answer |
|---|---|
| Is my usage shared with the team? | No. Each person has their own allowance. |
| How often does it reset? | Rolling 5-hour session window, plus a weekly allowance. Not a fixed daily clock. |
| What burns usage fastest? | Long documents pasted in, very long single chats, back-to-back heavy analysis |
| How do I stretch it? | Group related questions into one message. Start a new chat per topic. |
| Where do I check? | Initials (bottom left) → Settings → Usage |
| What if I run out? | Not a dead end. Ask the plan Owner (Howie) about turning on usage credits. |

---

### 5. Prompting Habits

| Habit | Weak | Better |
|---|---|---|
| Say what and why | "Write a follow-up email." | "Write a follow-up to a PI firm contact, no response in 5 days, about a case-expense request. Friendly but direct." |
| Give context | (none) | "I'm a sales consultant at a pre-settlement funding company, I work with PI law firms..." |
| Ask for a format | (none) | "Put this in a table." / "Give me three short bullet options." |
| Iterate | Accept the first draft | "Make it shorter." "Expand on option two." |
| Ask Claude to ask questions | (none) | "Ask me whatever you need before you draft this." |
| One topic per chat | Drag every topic into one thread | New topic → new chat. Old threads reprocess everything, which burns usage. |

**Bonus:** Save a paragraph of standing context (your role, what Capital Financing does) somewhere you can copy-paste from, instead of retyping it each time.

---

### 6. By Role

| Role | What Claude does well for you |
|---|---|
| Intake/underwriting support | Clean up a messy intake email, draft a missing-documents request, explain unfamiliar case terms. Not the approve/decline call. |
| Sales | Outreach and follow-up drafts, call talking points, role-play a hard conversation, organize a stack of conference contacts. |
| Contracting/agreements | Cover email language, pre-send checklists, summarize a long thread into "what's still outstanding." |
| Process documentation | Describe the process out loud, Claude turns it into a structured SOP. |
| Leadership/coordination | One-on-one talking points against KPIs, meeting recaps from a voice memo, devil's advocate on a people decision. |

---

### 7. Prompt Library

Paste in, swap the bracketed parts.

#### Ops

**Clean up a messy intake submission**
```
A law firm just sent me case info for funding [paste it]. Organize
this into a clean intake summary for underwriting, and flag anything
missing or unclear so I can go back to the firm before it holds
things up.
```

**Build a documents-still-needed tracker**
```
Here's our open case-expense files and what each is waiting on [paste
it]. Organize into a tracker: what's missing, how long outstanding,
which to chase first.
```

**Turn a process into an SOP**
```
I'm going to describe how I handle [task]. Ask me questions one at a
time until you have enough detail, then write it up as a numbered
SOP.
```

**Prioritize your AR follow-up list**
```
Here's my open AR files with balance, days outstanding, relationship
notes [paste it]. Rank which to prioritize this week and why, using
our usual cadence rules as a starting point.
```

#### Business Development (Financial Consultants)

**Plan your week against your KPIs**
```
Howie gave me targets for this [week/month]: [list them]. Ask me
where I stand against each one and what's getting in the way, then
build a realistic plan: daily priorities, how many touches I need,
what to stop letting slide.
```

**Triage your pipeline**
```
Here's where my open opportunities stand [paste or describe]. Tell me
which are stalling, which need a touch today, and which are worth
letting go of.
```

**Prep for a strategy call**
```
I have a Strategy Call with a law firm interested in case-expense
funding. Ask me what you need about the firm, their caseload, and
what they want, then build talking points and a natural transition
into scheduling the Onboarding Call.
```

**First post-onboarding follow-up**
```
I finished an onboarding call with a new firm for case-expense
funding. They'll send their first referral by [date], [contact] is
our point person. Draft a short, warm follow-up confirming this,
reconfirming the date. Not a hard sell.
```

**Score a prospect firm using public information only**
```
I'm evaluating [Firm Name] and only have public information, no
revenue or client volume. Using their website, reviews, published
case results, years in business, and case types, build a 1-10 score
with the specific green flags and red flags behind it. Be clear about
what you couldn't verify.
```

---

### 8. Skills

A Skill is a saved set of instructions for a task you do repeatedly. Build once, run with `/` plus the details that change.

| Step | How |
|---|---|
| Build one | New chat → describe the task in plain language → the built-in **Skill Creator** Skill writes it and adds it to your list |
| Run one | Type `/` in a new chat, pick the Skill, fill in the details |
| Share one | Team plan means a Skill one person builds can be shared across the team |

**Examples in use:** a prospect-research Skill (firm name + URL in, gap snapshot out), a call-prep Skill (company + attendees in, prep sheet out).

---

### 9. Other Features

| Feature | What it does | Where |
|---|---|---|
| Model choice | **Haiku** = fast, lightweight. **Sonnet** (default, currently Sonnet 5) = reasons through the problem, better for anything with real judgment. Names run short → long: Haiku, Sonnet, Opus. Don't compare the version number to ChatGPT's, the two companies number differently. | Picker next to the send button |
| Projects | Holds a group of related chats and reference documents so you stop re-uploading and re-explaining. Can be shared with teammates. | Left sidebar |
| Artifacts | A saved, separate panel for anything substantial Claude builds: a document, a spreadsheet, a small interactive tool. | Appears automatically when relevant |
| Scheduled Tasks | Runs on a recurring schedule without asking each time, e.g. a morning summary at 8:30 AM, a weekly news digest on specific firms. | Set up per-task |
| Memory | Two separate toggles, both off by default: **Generate memory from chat history** (builds a running profile of your role/preferences) and **Search and reference chats** (recalls past conversations). Same sensitive-data judgment as Section 2 applies. | Settings → Usage → Memory |

---

### 10. Do's and Don'ts

| Do | Don't |
|---|---|
| Treat it like a conversation, say "try again" or "make it shorter" | Paste full SSNs, bank details, or complete real client files |
| Give real context about your role and goal | Assume the first draft is final |
| Ask it to ask you questions when unsure what matters | Trust names, numbers, dates without checking the real file |
| Start a new chat for a new topic | Panic at a usage limit, it resets, and credits can be turned on |

---

## Next steps

- Confirm this stays current as new features roll out.
- Pin or link from wherever the team keeps shared resources.
