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

**Don't just explain it — demo it live**, using a real Capital Financing scenario so the team sees their own job in it immediately. Suggested live demo (pick whichever fits the room, or do two):

1. **Sales follow-up example.** Type into Claude, live, on screen:
 > "I need to follow up with a law firm contact from a conference two weeks ago about case-expense funding. Ask me whatever questions you need before you draft it."
 Let the group watch Claude ask back (tone? how many touches so far? what was discussed? deadline pressure?). Answer a couple live, show the resulting draft is noticeably better than a cold one-shot attempt.

2. **SOP-writing example.** Same move, framed for ops:
 > "I'm going to describe how I currently handle [a task]. Ask me questions one at a time until you have enough detail, then write it up as a clean step-by-step doc."
 This is exactly how the SOPs already being built for this project got started — worth saying out loud, it makes the technique concrete and already-proven.

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
- **The model picker** (next to the send button) — shows which Claude model is active; this can generally be left alone, but worth knowing it's there and not a mystery setting.
- **Copy / thumbs up-down / retry** under each response — copy pulls the text out to paste elsewhere; retry asks Claude to try again if a response missed the mark.
- **Artifacts** — when Claude produces something substantial (a document, a table, a piece of writing meant to be reused), it opens in a separate panel to the side instead of sitting in the chat — that's what lets you edit or export it cleanly.

**4. Settings — the two or three that matter for this team**
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

- Confirm which scenario(s) to use for the live "ask me questions" demo — sales follow-up and SOP-writing are drafted above as options; swap for whatever's most relatable to who's actually in the room.
- Decide whether to actually build one real Project live during the session (e.g. a shared "Follow-Up Emails" Project) as the UI walkthrough's worked example, rather than a hypothetical — likely stickier if time allows.
- Send `20260710_claude-intro-training-capital-financing.md` as the post-session leave-behind.
