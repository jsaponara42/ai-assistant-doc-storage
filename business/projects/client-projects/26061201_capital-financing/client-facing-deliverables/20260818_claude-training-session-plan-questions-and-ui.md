---
title: "Claude Training Session Plan — Ask-Questions Technique & UI Walkthrough"
date: 2026-08-18
tags: [client, project, ai, training]
ai: claude
status: ok
---

# Claude Training Session Plan — 1 Hour, Capital Financing Team

**A live-session script for tomorrow's training, focused on two things: getting Claude to ask *them* questions instead of chasing the "perfect prompt," and a hands-on tour of the interface.**

## Summary

Narrower and more hands-on than the full intro doc (`20260710_claude-intro-training-capital-financing.md`). That doc stays useful as a leave-behind reference — this is the actual run-of-show for the 1-hour live session, built around two things: (1) the "ask me questions" technique as the core prompting habit, taught by doing it live rather than explaining it, and (2) a guided walkthrough of the Claude.ai interface — sidebar, new chat, Projects, model picker, settings — so the basics stop being a source of hesitation.

## Context

Team is non-technical and new to LLMs. The full intro doc already covers this ground in writing (see its Section 4, point 5, and Section 6), but a live session needs a tighter arc: less reading, more doing. This plan assumes ~60 minutes, screen-shared from Claude.ai (web), with the team following along on their own accounts where possible.

## Content

---

### Session Arc (60 min)

| Time | Segment |
|---|---|
| 0:00–0:05 | Framing — why these two things, not everything |
| 0:05–0:30 | Part 1: Ask Claude to ask you questions |
| 0:30–0:55 | Part 2: UI walkthrough |
| 0:55–1:00 | Wrap-up, leave-behind doc, Q&A |

---

### 0:00–0:05 — Framing

Open with why this session is narrow on purpose:

> "You don't need to become prompt engineers. You need two habits: know where things are on screen, and know that you can hand Claude the driver's seat on figuring out what to ask you. That's it — that's the whole session."

Mention the full written guide (`20260710` doc) exists as a leave-behind for anything not covered live today — email/Slack it after, don't walk through it now.

---

### 0:05–0:30 — Part 1: Ask Claude to ask you questions

**The idea, in one line:** instead of trying to write the "perfect" instruction up front, tell Claude to ask *you* the questions it needs first. This is the single habit most worth building — it removes the pressure to know exactly what to say.

**Don't just explain it — demo it live, as one continuous chain**, using a real call transcript so the team watches Claude go from raw input to a finished, shareable deliverable in a single thread. This also happens to be the best possible demonstration of "Claude as thought partner, not spell-checker" — it's doing real synthesis work, not just cleaning up your sentences.

**Before the session:** pick a real discovery-call or client-call transcript you have on hand, and strip or swap out anything identifying (plaintiff names, case specifics, settlement figures) — placeholder names are fine. If you redact it live on screen and say why you're doing it, that's a free, concrete callback to the data-safety section of the leave-behind doc, better than a slide.

**The chain, live, in one chat:**

1. **Summarize.** Paste the (redacted) transcript:
 > "Summarize this call transcript into a few clear bullet points I could hand to someone with no context, and flag anything that still needs a decision or follow-up."
 Let the room see it turn 20 minutes of rambling conversation into something scannable in seconds.

2. **Turn it into a follow-up email — the ask-questions way.** Same chat, no re-pasting:
 > "Now draft a follow-up email based on that call. Ask me whatever you need first — who it's going to, the tone, what happens next."
 Answer Claude's questions live. This is the ask-questions technique landing a second time, but now it's obviously *useful* rather than a rule you were told to follow.

3. **Turn it into a document to share with the team — and ask for it as an actual Word file.** Same chat again:
 > "Now turn that summary into a one-page document I can share with the team — give it to me as a Word document."
 Say the "as a Word document" part out loud and deliberately — it's the one instruction that matters here. Claude will generate an actual downloadable `.docx` file rather than just formatted text in the chat window, which is what this team actually needs since everyone works in Word. This will very likely render as an **Artifact** (a separate panel next to the chat) — a natural moment to point that out, before it comes up again in the UI walkthrough.

**Then hand it to the room.** Ask each person (or pairs) to type the same "ask me questions first" framing into their own chat, using a real task they actually have this week. Give this 8–10 minutes of hands-on time — this is the part that actually builds the habit, not the demo.

**Push the demo one step further — show it's not one-and-done.** Once Claude hands back a decent draft, don't stop there on screen. Say out loud what you're doing and type it live: *"Great — now do the same thing but for [a related scenario]."* or *"Good, now make that shorter."* Let the room see Claude build on what it already knows rather than starting over. Then make the other half of the point explicit: *"If I were switching to something totally unrelated right now — not a follow-up, a new topic — I'd start a fresh chat instead of piling it into this one. Old, unrelated threads quietly eat more of your usage because Claude re-reads the whole thing each time."* This is the natural moment to say it, right after they've watched a thread actually get better through iteration.

**Close the segment with the reframe:**

> "You're not trying to write the perfect prompt. You're trying to start the conversation. If you're not sure what details matter, that's Claude's job to figure out — just say so. And once you're in a good conversation, keep going — you don't have to start from scratch every time."

---

### 0:30–0:55 — Part 2: UI walkthrough

Screen-share Claude.ai and walk through live, letting people follow along on their own screens rather than just watching.

**1. The left sidebar (home base)**
- **New chat** — top of the sidebar. Starts a fresh conversation with no memory of other chats. Rule of thumb: new topic = new chat.
- **Chat history / Recents** — every past conversation, searchable. Click any past chat to pick it back up.
- **Starred** — pin important chats or Projects here for one-click access; useful for anything used weekly (e.g. a standing follow-up-email chat).
- **Projects** — covered in detail below.

**2. What a Project actually is**
This is worth slowing down on — it's the single highest-leverage feature for a team that repeats the same kind of work.
- A Project is a **self-contained workspace**: its own chat history, plus a shared knowledge base and instructions that every chat inside it automatically gets.
- Two things live in a Project: **Project instructions** (a standing "here's who you are, here's the tone/format I want" note that applies to every chat in it) and **Project knowledge** (uploaded files — templates, SOPs, past examples — that Claude references automatically, no re-uploading or re-explaining each time).
- Concretely for this team: a "Case-Expense Onboarding Emails" Project with the firm-onboarding template and tone guide uploaded once, instructions set ("write in our voice, keep it under 200 words"), and every new chat inside it just works — no repeating context.
- **On the Team plan specifically:** Projects can be shared with the rest of the org, so a Project one person builds (the follow-up-email one, for instance) can be handed to the whole team instead of everyone rebuilding it solo.
- How to create one live: click **Projects** in the sidebar → **+ New Project** → name it → add instructions and/or upload a file or two → start chatting inside it.

**3. In the chat window itself**
- **The "+" button** (bottom left of the message box) — attach files, images, or documents to a message.
- **The model picker** (next to the send button) — worth actually explaining, not skipping past. Claude offers a few models, and the trade-off is speed vs. depth, not "better vs. worse":
  - **Haiku** is the fast, lightweight model — near-instant answers, good for quick questions or simple formatting where you don't need deep reasoning.
  - **Sonnet** (the default for most chats) actually "thinks" — it can pause, reason through a problem step by step, and iterate before answering, which costs a bit more time but gives noticeably higher-quality output on anything that takes real judgment (an SOP, a nuanced email, the transcript demo above).
  - **Worth naming directly if anyone's compared Claude to ChatGPT and found it slower:** that's almost always this setting, not a Claude limitation — ChatGPT's fast default is roughly Haiku's equivalent. Claude can be switched to Haiku for quick stuff too; the difference is Claude defaults to the more thoughtful model rather than the fastest one.
- **Copy / thumbs up-down / retry** under each response — copy pulls the text out to paste elsewhere; retry asks Claude to try again if a response missed the mark.
- **Artifacts** — when Claude produces something substantial (a document, a table, a piece of writing meant to be reused), it opens in a separate panel to the side instead of sitting in the chat — that's what lets you edit or export it cleanly. This is what you'll have already seen once, in the Word-document step of the Part 1 demo.

**4. Memory — Settings → Usage → Memory (or Settings → Capabilities on some accounts)**
Worth calling out by name, especially if anyone in the room has used ChatGPT and liked that it "remembers" them.
- Two separate toggles: **Generate memory from chat history** (Claude builds up a running profile of things you've told it — your role, your preferences, recurring context — so you stop re-explaining yourself every chat) and **Search and reference chats** (lets Claude look back through past conversations when you ask something like "what did we discuss about the Smith file last week?").
- Claude has this too, off by default — it's not something Claude lacks and ChatGPT has, it's just a setting nobody's turned on yet.
- Worth a one-line privacy note here, tying back to Section 2 of the leave-behind doc: memory is meant for professional context (your role, your preferences, recurring project names), not a place to store anything you wouldn't otherwise want retained — same judgment call as everything else in this training.

**5. Settings — the few that matter for this team**
Click your initials/profile icon (bottom left) → **Settings**.
- **Usage** — shows two progress bars: how much of your current 5-hour session you've used, and how much of your weekly allowance is left, plus reset times for each. Worth walking through live once so nobody's first encounter with it is a "you've hit your limit" screen — tie this directly back to the new-chat-vs-keep-going point from Part 1: this is the page that shows *why* that habit matters.
- **Appearance** — font size, dark/light mode, dyslexic-friendly font option if useful for anyone.
- **General** — includes things like voice language, if anyone uses voice input.
- Skip everything else live — it's mostly account/billing detail that Howie or the plan Owner handles, not day-to-day relevant.

**Leave 5 minutes here for people to click around on their own screen** while you're available to answer "wait, where's—" questions. This sticks far better than watching.

---

### 0:55–1:00 — Wrap-up

- Send the full written guide (`20260710` doc) afterward as a reference — don't re-teach it live, just point to it.
- Remind the room of the one habit worth remembering: *"When in doubt, ask Claude to ask you questions first."*
- Open the floor for anything that came up during the hands-on minutes.

---

## Next steps

- Pick the actual transcript for the live demo and redact/anonymize it beforehand (plaintiff names, case specifics, settlement figures) — do this ahead of time, not live, so the session doesn't stall on it.
- Decide whether to actually build one real Project live during the session (e.g. a shared "Follow-Up Emails" Project) as the UI walkthrough's worked example, rather than a hypothetical — likely stickier if time allows.
- Send `20260710_claude-intro-training-capital-financing.md` as the post-session leave-behind.
