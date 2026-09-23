---
title: "Stage 1 Intake Form Design — Close Q4 Strong Funnel"
date: 2026-09-23
tags: [strategy, project]
ai: claude
status: ok
---

## Summary
Full design for the shared Stage 1 intake form that feeds both free magnets (Competitive Reality Check, Risk Exposure Map) and Stage 2 qualification. About 10 screens, about 5 minutes, mostly tap-to-select with two voice-dictation prompts, plus a built-in mini tutorial on using device dictation. The backend pipeline reads the prospect's website after submission, so the form skips anything the site can answer.

## Context
First Stage 1 build task from [[20260922_close-q4-strong-entry-offer]]. The design works backward from what the analysis engine must produce. The key constraint: the form never pulls data live, but the backend automation can read the website after submission. There's plenty of time for that because the report is held a full business day before delivery.

## Content

### Design principles
1. **Work backward from the outputs.** Every question feeds at least one of three things: the Risk Exposure Map / Manual-Process Cost Estimate, the Competitive Reality Check, or Stage 2 qualification. Nothing is asked "just in case."
2. **Taps for numbers, voice for stories.** Structured data (size, frequency, role) comes from tap-to-select ranges. Rich detail comes from two voice prompts.
3. **Never ask for "hours wasted."** Ask how often something happens and how long one round takes. The engine does the math, which is more accurate and more believable.
4. **Anchor voice prompts on the last real time it happened.** This gets concrete steps, tools and names instead of vague summaries. A short checklist of what to mention sits under each prompt.
5. **Depth is optional.** The second process and the competitor question can be skipped, and each says what it adds.
6. **Don't ask what the website answers.** The backend reads the site. Industry (Screen 1) is the one deliberate exception, kept as the easiest first tap and as a check when the site is unclear.

### Question set

**Opening screen:** "About 5 minutes. Talking is faster than typing." Includes the collapsible dictation tutorial (see below). The copy differs by hook, but the form behind it is the same.

1. **What kind of business do you run?** (tap) Good-fit industries from Step 1, plus "Other."
2. **Where should we send your report?** First name, email, business name, and **website (required)**, with a "We don't have one" checkbox. Email is captured early so abandoned forms can get a follow-up, and progress saves at each step.
3. **How big is the team?** (tap) 1–9 / 10–24 / 25–49 / 50–99 / 100–249 / 250+. Number of locations is inferred from the site; if the site doesn't show it, the estimate scales off headcount.
4. **What's your role?** (tap) Owner/Founder, CEO/President, Operations leader, or Other.
5. **Where does your team's time go?** (tap, pick up to 3) Options: answering inquiries and scheduling, quotes and estimates, re-entering data between systems, invoicing and collections, pulling reports together, staff scheduling and onboarding, inventory and purchasing, following up with leads, paperwork and documents. These map to the Teardown's business-unit coverage map.
6. 🎙️ **"Pick the one that frustrates you most. Walk us through the last time it happened, start to finish."** Checklist under the prompt: what kicks it off, who handles it, what apps or paper they touch, where it gets stuck or redone.
7. **For that process** (three taps):
   - How often: a few times a week / daily / 5–20 a day / 20+ a day
   - Time per round: under 5 min / 5–15 / 15–30 / 30–60 / 1–2 hrs / half a day or more
   - Who does it: you / a manager / office or admin staff / frontline staff / spread across people
8. **Add a second one?** (optional, about 1 extra minute) Repeats Screens 6 and 7.
9. **What runs the back office?** (tap, multi-select) Accounting software, spreadsheets, paper or whiteboards, industry-specific software. Customer-facing tools (booking, chat, e-commerce, email marketing) are detected from the site instead. Then: **Where are you with AI today?** Haven't tried it / a few people use ChatGPT on their own / tried a tool that didn't stick / using it in at least one process.
10. **How do most new customers find you?** (tap) Referrals or repeat, local search or walk-in, online ads, marketplaces, outbound sales. This largely decides how exposed they are for the Risk Exposure Map, and doubles as an ICP check: heavy "referrals" answers may signal a relationship-driven business that isn't a fit.
11. 🎙️ **(Optional) "What have you seen others in your industry doing with AI, or what worries you about it?"** Feeds the Competitive Reality Check and gives us their own language for copy.
12. **Last one, so recommendations fit your business:**
    - Annual revenue range (tap): under $1M / $1–3M / $3–10M / $10–25M / $25M+
    - "If the report showed a clear opportunity, what's most likely?" We'd fix it ourselves / we'd bring in help if the numbers made sense / just gathering information for now

    This is the softened replacement for a direct budget question, addressing the opt-in friction watch item. An optional "first project size" range question can be added later if conversion data shows room for it.

### Dictation mini tutorial (built into the form)

The form uses the device's built-in dictation (speech-to-text), not a custom recorder. Most people have never used it, so the form teaches it in two places:

- **Opening screen:** a short collapsible "How to talk instead of type" section.
- **Each voice prompt:** a small "🎙️ How do I talk instead of type?" link that expands the same instructions.

**Show the right instructions automatically.** Detect the device (iPhone, Android, Mac, Windows) and show only the matching steps, with a "Using a different device?" link to the others.

**iPhone**
1. Tap inside the answer box so the keyboard opens.
2. Tap the **microphone icon** on the keyboard (bottom right, or next to the space bar).
3. Talk normally. Your words appear as you speak.
4. Tap the microphone again, or tap anywhere in the box, when you're done.
- No microphone icon? Go to **Settings → General → Keyboard** and turn on **Enable Dictation**.

**Android**
1. Tap inside the answer box so the keyboard opens.
2. Tap the **microphone icon** on the keyboard (usually top right of the keyboard, or near the space bar).
3. Talk normally, then tap the microphone again to stop.
- No microphone icon? Samsung and some other keyboards hide it. Look for it in the keyboard's toolbar, or install/switch to **Gboard** in your keyboard settings.

**Mac**
1. Click inside the answer box.
2. Press the **Fn key twice** (on newer keyboards it may be the 🌐 Globe key or a 🎤 microphone key).
3. Talk normally. Press **Fn** again, or **Esc**, to stop.
- Nothing happens? Go to **System Settings → Keyboard → Dictation** and turn it on. Allow microphone access if asked.

**Windows**
1. Click inside the answer box.
2. Press the **Windows key + H**.
3. Talk normally. Press **Windows key + H** again, or click the microphone, to stop.
- Nothing happens? Make sure your microphone is on, and allow access if Windows asks. Voice typing needs an internet connection.

**Tips shown under every device's steps:**
- Talk like you're explaining it to a new employee. Pausing is fine.
- Don't worry about punctuation or perfect wording. We read for meaning.
- Glance over it before continuing. Dictation sometimes mishears names and software.

**Build notes:**
- Test the tutorial on real devices (iPhone, a Samsung phone, a Pixel, Mac, Windows) before launch. Icon locations shift between OS and keyboard versions.
- If the form builder offers its own record-and-transcribe button, the tutorial becomes a fallback rather than the main path.

### Backend website read (runs after submission, before AI analysis)

What the site read opens up:
- **Manual-process signals as supporting evidence:** "call to book," "email us for a quote," printable PDF forms, no online payment, job applications by email, contact form with no promised response time. Strongest when they match what the prospect reported.
- **Real competitor comparison for the Competitive Reality Check:** the site gives their niche and service area, so the pipeline can find comparable local competitors and check what they visibly offer (online booking, chat, instant quotes, text updates). Reading public pages is passive, unlike the rejected live contact-form test, so it raises no consent concern.
- **Concrete customer-facing risk for the Risk Exposure Map:** after-hours inquiries with no response path, slow quote turnaround, no self-serve options. The "What AI Sees" idea ([[20260814_what-ai-sees-lead-magnet]]) may fit here as an extra exposure angle.
- **Personalization:** the report can refer to their actual services, pages and wording, which makes the one-business-day delay believable.
- **Qualification check:** number of locations, range of services, and a careers page (a growth signal) help confirm the size they reported.

Guardrails:
- **Dollar math comes only from form answers.** Site signals can add or strengthen findings, but never create hours or dollar figures by themselves.
- **Site findings are phrased as observations,** e.g. "From your site, it looks like quotes are handled by email." Sites are often out of date.
- **Graceful fallback:** if there's no site, or it can't be read well, the report runs on form answers alone.
- **Reviews (Google reviews via the official API) are a later version:** doable, but they add cost and terms-of-service considerations.

### How the answers become the estimate
Frequency × time per round (Screen 7) gives hours per week. Multiply by 50 working weeks for hours per year. Multiply by a role-based hourly cost (defaults by role and industry, including overhead) for dollars. Report both, as ranges, leaning conservative. When the owner does the work, value their time by what else they could be doing rather than a wage. The voice answer supplies the specifics (tools, handoffs, rework). If voice and tap answers conflict on a number, the tap answers win.

Possible later addition: if a voice answer comes back thin, the AI asks one follow-up question before the form continues. Held for now because of build complexity.

## Next steps
- **Built in Jotform (2026-09-23):** https://www.jotform.com/build/262656939909073. Device detection replaced with an optional "Show me how on: iPhone / Android / Mac / Windows" choice that reveals the matching dictation steps. Hidden fields added for `hook` and UTM parameters so the engine knows which landing page sent each lead. Needs a manual review pass: brand colors/fonts, conditional logic (no-website checkbox, second process, tutorial), progress bar, save-and-continue, and partial-submission capture.
- Build and test on real devices (iPhone, Samsung, Pixel, Mac, Windows), especially the dictation tutorial.
- Next linear build task: the Manual-Process Cost Estimate logic in implementation detail (role/industry hourly defaults, range math, owner-time valuation, how site signals attach to findings).
- Then the backend site-read step spec: what gets extracted, competitor discovery method, fallback behavior.
