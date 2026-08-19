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

**One habit worth building early: Claude is tuned to be agreeable.** The version of this technology that took off in 2021 went through a final training step where people ranked responses, and the responses people ranked highest were the ones that were affirming — telling the user they were right, that it was a great question, that their idea was strong. That habit got baked into how these tools respond. In practice, this means Claude will rarely push back hard on you unprompted, even when it should. It's still genuinely useful — but if you want honest pushback rather than agreement, ask for it directly: *"Be critical of this,"* or *"Tell me what's wrong with this approach before you tell me what's right."*

---

### 2. A Word on Sensitive Data — Read This First

This is a financial services business handling plaintiff and law firm data — SSNs, bank information. A few habits to build in from day one:

- **Don't paste full SSNs, or bank account/routing numbers into Claude.** 

This isn't about mistrust of the tool — it's the same instinct you'd already apply to any outside system.

---

### 3. Why We're All on a Team Plan (Not Personal Accounts)

If you've used a personal ChatGPT or Claude account before, you might wonder why we're doing this through one shared Capital Financing Team plan instead. A few concrete reasons:

- **One change benefits everyone at once.** If someone builds a Skill (see Section 8) that solves a recurring task the right way, it can be shared across the whole team instantly — nobody else has to solve the same problem from scratch.
- **Connectors are set up once, centrally.** A Connector is how Claude links to an outside system — for example, if we connect Claude to SharePoint so it can read documents stored there, that connection is set up once for the organization instead of every person configuring their own.
- **Data security.** This is a financial services business handling plaintiff names, firm contacts, and other confidential information. A free personal account (ChatGPT or Claude) does not come with the same data protections as a paid Team plan. The Team plan is what makes it safe to use Claude with real work information in the first place — see Section 2 for the specifics on what should and shouldn't be pasted in.

Bottom line: the Team plan means better security for confidential data, and it means good solutions spread across the team automatically instead of everyone reinventing the wheel.

---

### 4. How Usage Works (so nobody gets blindsided)

Claude Team gives each person their own seat with its own usage allowance — **your usage is separate from everyone else's.** If Audrey uses up her limit for the moment, it doesn't affect Brian's or Christy's — each person's included usage is their own, so one person reaching their limit doesn't slow anyone else down.

A few things worth knowing:

- **Usage resets on a rolling window, not once a day.** You get a chunk of usage, and if you use it all up, you wait for it to refresh rather than being cut off permanently. If you hit a limit mid-task, it's not a bug — it just means that window is used up.
- **Longer, more complex conversations use more of your allowance.** Pasting in a huge document, having a very long back-and-forth in one chat, or asking for a lot of back-to-back heavy analysis will burn through usage faster than short, focused requests.
- **A few habits stretch your usage further:** group related questions into one message instead of sending them one at a time, and take a moment to make sure your message is clear and complete before sending so you need fewer follow-ups. Starting a fresh chat for a new topic (instead of one giant never-ending thread) also helps.
- **If you do run out**, you're not stuck — the account Owner can turn on "usage credits," which lets people keep working past their included limit instead of getting blocked. If this happens to you regularly, flag it to whoever manages the Claude account (Howie or whoever the plan Owner is) rather than assuming you're locked out for good.

**Bottom line:** it's not unlimited, but running out isn't a dead end — it's a "wait a bit or ask for more" situation.

**How to check where you stand.** Click your initials (bottom-left corner) → **Settings** → **Usage**. You'll see two progress bars: how much of your current session you've used (Claude runs on a rolling **5-hour session window**, not a fixed daily clock), and how much of your **weekly** allowance is left, plus when each one resets. It's less "check once a day/month" and more "check whenever you're curious or about to start something big" — but that page is the one place that has the real numbers.

---

### 5. Basic Prompting — 5 Habits That Make a Real Difference

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

**Bonus habit: build yourself a few "prompt modules."** If you find yourself retyping the same background every time — who you are, what your role is, a paragraph on what Capital Financing does — save that as a short paragraph somewhere easy to grab (a notes app, a doc). Then it's copy-paste instead of retyping, every time you start a new chat that needs that context.

---

### 6. What This Looks Like In Your Actual Job

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

### 7. Try These Prompts — Copy, Paste, Edit

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

**5. Score a prospect firm using only public information**
```
I'm evaluating [Firm Name] as a prospect and I don't have access to
their revenue, client volume, or internal financials — just what's
publicly available. Using their website, online reviews, case results/
verdicts they publicize, how long they've been in business, and the
types of cases they handle, help me build a 1-10 score for how strong
a prospect they are, with the specific green flags and red flags you
found driving that score. Be clear about what you couldn't verify.
```
*Why this works: it's the same judgment call you'd make manually (reputation, longevity, case mix) — Claude just does the research and organizes it into a scored, defensible view faster than you could by hand.*

---

### 8. Skills — Turning a Repeated Task Into One Command

If you find yourself explaining the same kind of task to Claude over and over — "research this firm and tell me their gaps," "prep me for a call with this company," "here's how I write up an SOP" — that's a sign it should become a **Skill**.

A Skill is a saved set of instructions you build once. After that, instead of retyping the full explanation every time, you type `/` in a new chat, pick the Skill from the list, fill in just the one or two details that change (a firm name, a website URL), and Claude runs the whole thing.

**How to build one — you don't have to write it yourself.** Every Claude account comes with a built-in Skill called **Skill Creator** (type `/` in a new chat and it will be in the list). Open a new chat, describe the task you want to turn into a Skill in plain language — what you're trying to accomplish, what info you'd give it, what you want back — and Skill Creator will build the instructions for you and add it to your Skill list. You don't need to know how to write a technical prompt; you just need to describe the task clearly, the same way you would to a new hire.

**A couple of real examples from how this gets used:**
- A prospect-research Skill: give it a firm name and website URL, and it comes back with a snapshot of gaps in their marketing/intake setup — something that would take an hour to research by hand comes back in under a minute.
- A call-prep Skill: give it a company name, website, and the names of who's attending, and it researches the company and the attendees and hands back a prep sheet before a call — useful when you only have a few minutes before a meeting.

**Because we're on the Team plan, a Skill someone builds can be shared with the rest of the team** — so once one person solves how to do a recurring task well, everyone benefits from it immediately instead of rebuilding it themselves.

---

### 9. Quick Do's and Don'ts

**Do:**
- Treat it like a conversation — you can always say "try again" or "make it shorter"
- Give real context about your role and goal
- Ask it to ask you questions when you're not sure what details matter
- Start a new chat when you're switching to a totally different topic

**Don't:**
- Paste in full SSNs, bank details
- Assume the first draft is final — push back on it like you would a first draft from a person
- Trust specific numbers, names, or dates it produces without double-checking against the real file
- Panic if you hit a usage limit — it resets, and credits can be enabled if it becomes a regular issue

---

### 10. More Features Worth Knowing: Model Choice, Projects, Artifacts, Scheduled Tasks & Memory

**Model choice — Sonnet vs. Haiku.** The model picker sits next to the send button. It's a speed-vs-depth trade-off, not "better vs. worse": **Haiku** is fast and lightweight — near-instant answers, good for quick, simple things. **Sonnet** (the default for most chats, currently Sonnet 5) actually "thinks" — it can pause and reason through a problem step by step before answering, which takes a bit longer but gives noticeably better output on anything with real judgment in it (an SOP, a nuanced email, prepping for a hard conversation). If Claude has ever felt slower than ChatGPT, that's almost always this setting — ChatGPT's fast default is roughly Haiku's equivalent, and Claude defaults to the more thoughtful model instead of the fastest one. You can switch to Haiku for quick stuff any time from that same picker.

*A memory trick for the model names:* Claude's models are named after lengths of written text, shortest to longest — **Haiku** (short) → **Sonnet** (a longer poem) → **Opus** (longer still). The version number after the name (Sonnet 5, Haiku 4.5) is just which generation it is — don't compare that number to ChatGPT's version numbers, since the two companies number things completely differently. What matters day to day is the name in front of the number, and for nearly everything you do, that name is **Sonnet**.

**Projects.** A Project is a dedicated space that holds a group of related chats and any documents you reference regularly, so you're not re-uploading the same files or re-explaining the same background every time you start a new chat on that topic. Because we're on the Team plan, a Project can also be **shared with specific teammates** — so if you build a Project for a recurring type of work, whoever you share it with sees the same context you've built up, instead of starting from zero.

**Artifacts.** When Claude produces something more substantial than a chat reply — a document, a spreadsheet, or even a small interactive tool (for example, a working calculator built for a website) — it shows up as an Artifact: a separate, saved panel you can view, keep working on, and come back to later, rather than a wall of text you'd have to scroll back through.

**Scheduled Tasks.** Claude can run a task automatically on a recurring schedule without you having to ask each time — for example, a morning email summary waiting for you at 8:30 AM, or a weekly digest of news from a specific set of law firms or a state you're tracking. Worth knowing about for anything you currently do the same way, by hand, on a recurring basis.

**Memory.** Click your initials → **Settings** → **Usage** → **Memory** (some accounts show this as Settings → Capabilities instead). Two separate toggles: **Generate memory from chat history** lets Claude build up a running profile of things you've told it — your role, your preferences, recurring project names — so you stop re-explaining yourself every chat. **Search and reference chats** lets Claude look back through past conversations when you ask something like "what did we discuss about that last week?" Both are off by default. If you've used ChatGPT and liked that it "remembers" you, this is the same idea — Claude just doesn't turn it on automatically. Same judgment call as everything in Section 2 applies here: memory is meant for professional context, not a place to store anything sensitive.

---

## Next steps

- Decide whether this is delivered as a live walkthrough session, a send-and-read document, or both.
- Confirm who the plan Owner is (for usage credit / limit questions) so the team knows who to flag to if they hit limits regularly.
- Consider a short follow-up session after 1-2 weeks of real use to collect questions and refine which example prompts actually get used.
