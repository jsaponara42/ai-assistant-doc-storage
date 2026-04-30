---
name: pi-firm-snapshot
description: "Generates a personalized 'Workflow Waste Snapshot' for one or more personal injury law firms using publicly available data. Use this skill whenever JC asks to research a PI firm, generate a snapshot, build a prospect snapshot, create a workflow snapshot, research a law firm for outreach, or analyze a firm's website. Also trigger on phrases like 'run a snapshot on', 'build a snapshot for', 'snapshot this firm', 'research this firm for outreach', or any time a firm name and/or website URL is provided in a prospecting or outreach context. If the user provides a firm name but no URL — or a URL but no firm name — ask for the missing piece before proceeding. If neither is provided, ask for both. Never skip the elicitation step."
---

# PI Firm Workflow Waste Snapshot

Generates a personalized, research-backed "Workflow Waste Snapshot" for a PI law firm using only publicly available data. The output is a rendered card widget with 3 specific workflow gaps, cost estimates, and a copy-as-email button — ready to send as cold outreach.

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

| Gap Category | Evidence Signal | Cost Frame |
|---|---|---|
| Intake speed / phone dependency | Phone-only CTA, no chat widget, no auto-response | Leads/month x case value |
| Review volume lag | Low count relative to years in operation | Missed reviews/year -> local SEO rank |
| Social audience not monetized | Followers + no retargeting or lead gen content | Recoverable signed-case value/year |
| Ad spend with weak landing page | Google ad -> homepage (not dedicated page) | Conversion rate loss x lead volume |
| Bilingual capability not leveraged | Spanish pages exist, no Spanish social outreach | Underserved audience opportunity |
| Manual follow-up signals | Reviews mentioning slow response, no CRM signals | Leads going cold x case value |

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
[Copy as email button]
```

**Cover note tone:** Written to the decision-maker by name if identifiable. Acknowledges something specific about the firm (awards, bilingual capability, case volume, years in operation) before pivoting to gaps. Never sounds like a template.

**Closing line:** Always ends with a single sentence inviting a short call to go deeper with internal data — never pitches the full engagement, never mentions price.

**Copy as email button:** Clicking copies the full snapshot as plain text — cover note, all three gaps with titles and cost estimates, closing line. Format should be paste-ready into an email client with no markdown symbols.

---

## Widget Visual Pattern

- Card: `border: 0.5px solid var(--color-border-tertiary)`, `border-radius: var(--border-radius-lg)`, padding 1.5rem
- Cover note: left-bordered blockquote (`border-left: 2px solid var(--color-border-tertiary)`, padding-left 14px)
- Each gap: blue left border (`border-left: 2px solid #378ADD`)
- Gap number label: small, `color: #185FA5`, uppercase, letter-spaced
- Gap title: `font-size: 14px; font-weight: 500`
- Cost badge: `background: #E6F1FB; color: #185FA5; font-size: 11px; padding: 2px 9px; border-radius: 4px`
- Closing line: italic, separated by `border-top: 0.5px solid var(--color-border-tertiary)`
- Copy button: top-right, `border: 0.5px solid var(--color-border-secondary)`, copies plain text on click
- All text uses CSS variables — never hardcoded colors

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
- [ ] Copy-as-email text is clean plain text with no markdown symbols
