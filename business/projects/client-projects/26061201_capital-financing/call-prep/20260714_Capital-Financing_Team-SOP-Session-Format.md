---
title: "Capital Financing — Team SOP Walkthrough Session Format"
date: 2026-07-14
tags: [client, project, task]
ai: claude
status: ok
---

# Team SOP Walkthrough — Session Format (Reusable for Thu/Fri and future sessions)

## Summary

The live-session script JC runs on both Thursday and Friday: walk each attendee through describing their workflow out loud (the "Easy SOP" method) while screen-sharing, then close with Claude Team setup — deferred to the end so setup hiccups don't eat into SOP time. Referenced by both day-specific call-prep docs rather than repeated in each.

## Context

Built from the existing [[20260617_Quick_SOP_Creation_Guide]] (the async, self-serve version of this method), adapted for a live, JC-led screen-share session with non-technical staff instead of someone doing it solo. Same underlying method — talk through the workflow, hand it to Claude, Claude structures it, Claude asks clarifying questions — just JC-driven instead of self-directed.

## Content

---

### Session Flow (same shape both days)

**1. Kickoff — 2 minutes**
Frame it simply: *"We're documenting how you actually do your job today — not how it should work, not the ideal version. That's what lets us find the real quick-win automations. There's no wrong answer here — if something's clunky or manual, say so, that's exactly what we want to hear."*

**2. Live SOP walkthrough — bulk of the call**
Screen-share a Claude chat. For each workflow (see the day-specific priority order in each call-prep doc), open with this prompt:

> I'm going to describe my role and how I currently handle **[workflow name]** at Capital Financing. Ask me clarifying questions one at a time as I go if anything is unclear. When I say I'm done, write up everything I've described as a clean, numbered, step-by-step SOP that someone with no context could follow. Flag anything ambiguous or unconfirmed as `[TO CONFIRM]` rather than guessing.

Then have the person talk it through out loud. If they stall or go vague, prompt them with these six questions (same checklist as the self-serve guide):
- What do you need to start this? (**Inputs**)
- Where does that come from? (**Source**)
- What software/tools do you touch? (**Systems**)
- Who else is involved, and what's their part? (**Owners**)
- What comes out the other end? (**Outputs**)
- Where does that output go — who or what system receives it? (**Hand-off**)

Let Claude ask its own follow-ups too — that's the point of the prompt above. Don't rush past them; the gaps Claude surfaces are usually the same gaps that make the process hard to hand off or automate.

**3. Wrap-up — how completed SOPs get to JC**
Not everything will get finished live — that's expected. For anything finished during or after the call:
- Save/export the finished SOP text from the Claude conversation (copy the final write-up Claude produced).
- Email it to JC at **`[TO CONFIRM — JC's preferred email/address for this]`** — a plain copy-paste into the email body is fine, no special formatting needed.
- No filename convention required on their end — JC will fold it into the vault.

**4. Claude Team setup — last, ~5 minutes, do not troubleshoot live**
Share the join link and have everyone click through and log in during the call:

```
https://claude.ai/join/org/Ccg9eZuKOphA-dMY23rWKw
```

Confirm each person can see they're in the Capital Financing workspace — that's the only success check needed live. **If anything doesn't work (login issue, wrong email, etc.), don't stop to fix it in the group** — tell them to message JC directly afterward and it'll get sorted one-on-one. This keeps one person's login problem from eating everyone else's time.

**5. What happens next**
Let the group know: once SOPs start coming in, JC may follow up individually if something needs more detail — a short one-on-one follow-up call is likely for at least one or two people, not a failure state, just normal next-pass clarification (same pattern as the `[TO CONFIRM]` items already in the existing workflow map).

---

## Next steps

- Fill in the actual email/submission channel before Thursday's call.
- After both sessions, fold any completed SOPs into `SOPs/` following existing naming (`YYYYMMDD_Capital-Financing_[Process-Name]_SOP.md`).
- Reuse this session-format doc for any future team SOP sessions rather than rewriting the script each time.
