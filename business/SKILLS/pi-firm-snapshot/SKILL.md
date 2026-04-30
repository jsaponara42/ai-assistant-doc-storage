---
name: pi-firm-snapshot
description: "Generates a personalized 'Workflow Waste Snapshot' for one or more personal injury law firms using publicly available data. Use this skill whenever JC asks to research a PI firm, generate a snapshot, build a prospect snapshot, create a workflow snapshot, research a law firm for outreach, or analyze a firm's website. Also trigger on phrases like 'run a snapshot on', 'build a snapshot for', 'snapshot this firm', 'research this firm for outreach', or any time a firm name and/or website URL is provided in a prospecting or outreach context. If the user provides a firm name but no URL — or a URL but no firm name — ask for the missing piece before proceeding. If neither is provided, ask for both. Never skip the elicitation step."
---
---

## name: pi-firm-snapshot description: 

---
"Generates a personalized, research-backed "Workflow Waste Snapshot" for a PI law firm using only publicly available data. The output is a rendered card widget with 3 specific workflow gaps, cost estimates, and two copy buttons — one for a teaser email (sneak peek of Gap 1 only, asking if they want the full thing) and one for the full snapshot. Email copy follows Blue Tusk brand and voice guidelines."

---
## Required Inputs

Before doing any research, confirm you have BOTH:

- **Firm name** — the full name as it appears publicly (e.g. "Giordano Law Offices")
- **Website URL** — the firm's primary website (e.g. https://gio-law.com)

If either is missing, ask for it before proceeding. Do not attempt to guess or infer the URL from the firm name.

**Elicitation prompt (use if inputs are incomplete):**

> "To generate the snapshot I need two things: the firm's name and their website URL. Which one are you missing?"

---

## Research Process

Run all three steps for each firm before writing the snapshot.

### Step 1 — Website fetch

Use `web_fetch` on the firm's URL. Extract:

- Primary intake CTA (phone, form, chat widget, text line)
- Staff count from attorney bios pages
- Practice area specificity (PI only vs. mixed)
- Any visible case management software or chat widget vendor
- Spanish-language or bilingual pages
- Blog recency (last post date if visible)
- Whether ads go to homepage or dedicated landing page

### Step 2 — Google search

Search: `[Firm Name] reviews Google` and `[Firm Name] [city] personal injury`

Extract:

- Google Business Profile star rating
- Visible review count across platforms (Google, Yelp, Avvo, Martindale)
- Review content — flag any mentions of "hard to reach," "never heard back," "had to follow up" (intake failure signals)
- Whether they appear as a paid Google result (running ads = active lead flow)
- Years in operation vs. review volume ratio

### Step 3 — Social/ads search

Search: `[Firm Name] Facebook` and check for Meta Ads Library signals.

Extract:

- Facebook page follower count and last post type (credibility vs. lead gen content)
- Whether they appear to be running Facebook/Instagram ads
- Any bilingual social content or community-specific targeting

---

## Gap Identification Framework

After research, identify exactly 3 gaps. Select from the categories below based on what the evidence actually supports — do not fabricate gaps not supported by the research.

|Gap Category|Evidence Signal|Cost Frame|
|---|---|---|
|Intake speed / phone dependency|Phone-only CTA, no chat widget, no auto-response|Leads/month x case value|
|Review volume lag|Low count relative to years in operation|Missed reviews/year -> local SEO rank|
|Social audience not monetized|Followers + no retargeting or lead gen content|Recoverable signed-case value/year|
|Ad spend with weak landing page|Google ad -> homepage (not dedicated page)|Conversion rate loss x lead volume|
|Bilingual capability not leveraged|Spanish pages exist, no Spanish social outreach|Underserved audience opportunity|
|Manual follow-up signals|Reviews mentioning slow response, no CRM signals|Leads going cold x case value|

**Rules for gap writing:**

- Each gap: 3-5 sentences max
- Write in second person ("your firm," "your intake process")
- Frame inferences as "firms like yours typically..." — never state as confirmed fact what you cannot verify
- Attach a specific cost estimate to every gap — ranges are fine, vague language is not
- Do not repeat the same gap category twice across the three gaps

---

## Output Format

Render a widget using `show_widget` with this structure for each firm:

```
[Firm name header + URL]
[2-3 sentence cover note — personal, direct, not salesy]
---
Gap 1: [Title]
[Observation] [Cost tag]

Gap 2: [Title]
[Observation] [Cost tag]

Gap 3: [Title]
[Observation] [Cost tag]
---
[Closing line — invites a call to go deeper with internal data]
[Copy Teaser Email button] [Copy Full Snapshot button]
```

**Cover note tone:** Written to the decision-maker by name if identifiable. Acknowledges something specific about the firm (awards, bilingual capability, case volume, years in operation) before pivoting to gaps. Never sounds like a template.

**Closing line:** Always ends with a single sentence inviting a short call to go deeper with internal data — never pitches the full engagement, never mentions price.

---

## Email Copy Rules (Blue Tusk Brand Voice)

All email copy generated by this skill must follow these rules. Read them before writing any subject line, preview text, or body copy.

### Voice

A well-connected business owner reaching out to a peer because he genuinely thinks he can help. High status, casual, not trying to prove anything. Not desperate. Short sentences. Questions over statements when possible. Specific over general.

### Grammar rules

- No em-dashes. Use a period or comma instead
- No rule of three (adjective, adjective, adjective). Use one strong word
- No negative parallelisms ("it's not X, it's Y") as a crutch
- No elegant variation — if you've named the subject, use the same word again
- Under 100 words of body copy per email
- One point per email, one ask per email

### Banned words

Do not use: additionally (to open), align with, boasts, bolstered, crucial, delve, enhance, fostering, garner, highlight/highlighted, interplay, intricate, key (as adjective), landscape (abstract), meticulous, pivotal, showcase, tapestry, testament, underscore (as verb), valuable, vibrant

### Subject lines

Understated. A topic, not a promise. Should sound like a real person wrote it between meetings.

- Good: "had a thought about your intake", "quick question about your team"
- Bad: "Increase your PI case sign rate by 40%", "Free workflow audit for PI firms"

### Preview text

Always: `{{firstName}},` + a question or tease that opens a loop. Never fully explain the email in preview text.

- Good: `{{firstName}}, do you know how much time your staff spends on automatable tasks?`

### Signature conventions

- Email 1 (Teaser): Full name + title — `John-Carlos Saponara / Founder, Blue Tusk LLC`
- Email 2 (Follow-up): First name only — `John-Carlos`
- Email 3 (Full snapshot): Full name + company — `John-Carlos Saponara / Blue Tusk LLC`

---

## Three-Email Sequence

This skill generates copy for exactly three emails. Each is available as a separate copy button in the widget. **Do not generate a fourth email or deviate from this structure.**

### Email 1 — Teaser (Day 1)

**Purpose:** Send a sneak peek of Gap 1 only. Ask if they want the full snapshot. Do not attach or include the full report. This protects email reputation — no attachments to cold leads.

**Structure:**

- Open with something specific and real about the firm (from research)
- One sentence introducing that you ran a quick look at their public presence
- Share the Gap 1 finding in 2-3 sentences: observation + cost estimate
- Ask if they want the other two findings sent over
- No pitch, no CTA to book a call yet

**Example frame (not a template — rewrite per firm):**

> Saw [Firm Name] has been running Google ads for a while. I noticed they go to your homepage rather than a dedicated page, which typically cuts conversion rate in half for PI firms. That's worth looking at if you're paying for clicks.
> 
> I pulled two other findings on your setup if you want me to send them over.

### Email 2 — Follow-up if no response (Day 4)

**Purpose:** One short nudge. Add a stat or reframe. Do not repeat Email 1.

**Rules:**

- Under 60 words
- Must be sequence-agnostic (cannot reference Email 1 directly)
- Leave the door open, no pressure
- One question only

### Email 3 — Full Snapshot delivery + CTA (Day 8, sent only if they reply to Email 1 OR as the final touch in a non-reply sequence)

**Purpose:** Deliver the full snapshot (all 3 gaps) inline in the email body — no attachment. End with a single CTA to book a call.

**Rules:**

- All 3 gaps summarized in plain prose, one short paragraph each
- Cost estimate included per gap
- Closing CTA: one sentence, calendar link implied (write as `[calendar link]` placeholder)
- Do not oversell — the data does the work

---

## Widget Visual Pattern

- Card: `border: 0.5px solid var(--color-border-tertiary)`, `border-radius: var(--border-radius-lg)`, padding 1.5rem
- Cover note: left-bordered blockquote (`border-left: 2px solid var(--color-border-tertiary)`, padding-left 14px)
- Each gap: blue left border (`border-left: 2px solid #378ADD`)
- Gap number label: small, `color: #185FA5`, uppercase, letter-spaced
- Gap title: `font-size: 14px; font-weight: 500`
- Cost badge: `background: #E6F1FB; color: #185FA5; font-size: 11px; padding: 2px 9px; border-radius: 4px`
- Closing line: italic, separated by `border-top: 0.5px solid var(--color-border-tertiary)`
- **Two copy buttons** in a row at the bottom:
    - "Copy Teaser Email" — copies Email 1 plain text only
    - "Copy Full Snapshot" — copies all 3 gaps as plain text (original behavior)
- Button style: `border: 0.5px solid var(--color-border-secondary)`, copies plain text on click
- All text uses CSS variables — never hardcoded colors

---

## Copy Button Behavior

### "Copy Teaser Email" button

Copies Email 1 as paste-ready plain text. Format:

```
Subject: [subject line]
Preview: [preview text]

[Email 1 body]

[Signature — Full name + title]
```

### "Copy Full Snapshot" button

Copies all 3 gaps as plain text — cover note, all three gaps with titles and cost estimates, closing line. Format should be paste-ready into an email client with no markdown symbols.

---

## Multiple Firms

If more than one firm is provided, process each sequentially and render a separate card for each. After all cards are rendered, add a plain text summary: "X snapshots generated — use the copy buttons to pull each one into your outreach."

---

## Quality Check (run before rendering)

- [ ] All 3 gaps are supported by actual research findings, not assumptions
- [ ] No gap category is repeated
- [ ] Every gap has a specific cost estimate (no vague language)
- [ ] Cover note references something specific and real about this firm
- [ ] Closing line does not pitch price or the full engagement
- [ ] Email 1 shares Gap 1 only — does not include Gaps 2 or 3
- [ ] Email 1 body is under 100 words
- [ ] Email 2 is under 60 words and sequence-agnostic
- [ ] Email 3 includes all 3 gaps inline, no attachment, ends with CTA
- [ ] No banned words used in any email copy
- [ ] No em-dashes in any email copy
- [ ] Subject lines are understated — topic, not promise
- [ ] "Copy Teaser Email" copies Email 1 only; "Copy Full Snapshot" copies all 3 gaps