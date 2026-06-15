---
name: ai-roadmap-call-prep
description: "Generates a complete Call Brief to prepare JC for an AI Roadmap Consultation intro call. Use this skill any time JC provides a company name, company website, and one or more people he'll be meeting with — regardless of industry. Triggers on phrases like 'prep me for a call with', 'generate a call brief for', 'I have a meeting with', 'build my prep doc for', 'call prep for', 'I'm meeting with [name] at [company]', or any time a company name + website + attendee name(s) are provided together. If any of the three required inputs are missing, ask for them before proceeding. Never skip the elicitation step. Always use this skill before a consultation intro call — even if JC doesn't say the word 'skill'."
---

# AI Roadmap Call Prep

Generates a research-backed Call Brief for the intro call of a Free AI Roadmap Consultation. Covers company, people, industry pain mapping, and sharp questions — all synthesized into a single scannable document.

---

## Required Inputs

Before starting any research, confirm you have all three:

1. **Company name** — the full name as it appears publicly
2. **Company website** — the primary URL
3. **People attending** — name(s) and title(s) of who JC will be meeting with

If any input is missing, ask for it before proceeding:

> "To prep the call brief I need three things: the company name, their website, and the name(s) and title(s) of who you'll be meeting with. What's missing?"

---

## Research Process

Run all four stages before writing the Call Brief. Do not skip stages or write the brief while research is in progress.

### Stage 1 — Company Research

**Goal:** Understand what the company does, how it operates, and where friction is most likely.

1. `web_fetch` the company website. Read the homepage, About page, and any services or products page. Extract:
   - What they sell or deliver
   - Who their clients or customers are
   - Approximate headcount (look for team pages, attorney bios, staff listings)
   - How long they've been in operation
   - Any visible tech stack signals (CRMs, chat widgets, scheduling tools, form builders)
   - Quality of their intake or contact experience (phone-only? form? live chat? automated?)

2. Web search: `[Company Name] LinkedIn`. Extract:
   - Total headcount and department breakdown
   - Recent hiring patterns — heavy admin/ops hiring signals manual process overload
   - Any recent company updates or announcements

3. Web search: `[Company Name] reviews` and `[Company Name] [city] [industry]`. Extract:
   - Google/Yelp/Glassdoor star rating and review volume
   - Review content — flag any "hard to reach," "never heard back," "had to follow up," or "disorganized" signals
   - Any press coverage, awards, or notable mentions

4. Web search: `[Company Name] Google ads` or check if they appear as a paid result. Active ad spend = active lead flow = likely intake and follow-up pressure.

5. Note: company name, industry/sector, approximate size, primary service or product, how long in business, any notable signals of growth, strain, or tech maturity.

### Stage 2 — Person Research

**Goal:** Understand who JC is actually talking to and what that means for the conversation.

For **each person** attending the call:

1. Web search: `[Person Name] [Company Name] LinkedIn`. Extract:
   - Title and how long they've been in this role
   - Background before this company (relevant prior industries or functions)
   - Whether they are a founder/owner vs. an operator/manager — this changes the conversation framing significantly

2. Check their company bio page if one exists. Note any language they use to describe themselves — mirroring their framing builds rapport.

3. Look for any public content (LinkedIn posts, interviews, podcasts, press quotes). This surfaces what they think about, what they're proud of, and occasionally what frustrates them.

4. Flag tenure context:
   - Under 18 months in role → likely actively hunting problems to fix, may be change-ready
   - Long-tenured founder → may be blind to their own bottlenecks, needs reframing, not convincing

### Stage 3 — Industry Pain Mapping

**Goal:** Anticipate the 3–5 most likely operational pain points before anyone names them.

This stage is about the industry, not the specific company. Every industry has structural inefficiencies that recur at similar firm sizes. Knowing them in advance sharpens questions and speeds pattern recognition during the call.

1. Identify the industry category from this list:
   - Legal / Law Firms
   - Healthcare / Medical Practices
   - Real Estate (Brokerage, Property Management, Commercial)
   - Construction / Trades / Contractors
   - Marketing / Creative Agencies
   - Financial Services (Accounting, Wealth Management, Insurance, Lending)
   - Professional Services (HR, Consulting, Staffing)
   - Retail / E-Commerce
   - Hospitality (Restaurants, Hotels, Events)
   - Education (Schools, Training, Tutoring)
   - Logistics / Supply Chain / Distribution
   - Nonprofit / Association
   - SaaS / Tech Company
   - Other (describe)

2. For the identified industry, answer these five questions. Use your training knowledge first; web search if the industry is unfamiliar or niche:
   - What tasks in this industry are still done manually by default, even at "modern" firms?
   - Where does client or customer communication typically break down?
   - What reporting, compliance, or documentation burdens are inherent to the industry?
   - Where do firms in this space lose revenue or time due to process gaps rather than strategy gaps?
   - Where does growth create new operational strain (what breaks at 5 people that didn't break at 2, or at 15 that didn't at 8)?

3. From your answers, extract the 3–5 most specific, most likely pain patterns for a firm of this industry and apparent size. Be concrete — not "communication problems" but "new client intake handled via phone tag, with no automated follow-up, so leads go cold before a consultation is ever booked."

4. For each anticipated pain, draft one sharp question JC can ask to confirm or surface it during the call. The question should feel natural — not like a survey item.

### Stage 4 — Call Brief Synthesis

**Goal:** Produce a single scannable document JC can read in under two minutes before the call.

Assemble and render the Call Brief using the format below. Render it as a widget using `show_widget`. Include a "Copy as Markdown" button that copies the full brief as clean plain text.

---

## Call Brief Format

```
# Call Brief — [Company Name]
**Date:** [call date if known, otherwise leave blank]
**Industry:** [industry]

---

## The Company
- **What they do:** [1–2 sentences]
- **Size:** [approximate headcount or size tier: solo / 2–5 / 6–15 / 16–50 / 50+]
- **Stage:** [startup / growth / established / mature]
- **Tech signals:** [any visible tools, CRMs, chat widgets, intake tech — or "none visible"]
- **Notable:** [anything that stood out — ad spend, reviews, recent growth, disorganization signals, press]

---

## The People

### [Person 1 Name] — [Title]
- **Tenure:** [how long in role]
- **Background:** [relevant prior experience in 1 sentence]
- **Frame:** [founder-owner / operator-manager / new leader / long-tenured]
- **Notable:** [any context about how they think, what they care about, or what they've said publicly]

### [Person 2 Name] — [Title] (if applicable)
(repeat structure)

---

## Anticipated Pains
1. [Specific pain #1 — tied to industry + size]
2. [Specific pain #2]
3. [Specific pain #3]
4. [Pain #4 if warranted]
5. [Pain #5 if warranted]

---

## Sharp Questions to Ask
- [Question to confirm or surface Pain #1]
- [Question to confirm or surface Pain #2]
- [Question to confirm or surface Pain #3]
- "What's taking the most time in your operation right now that you wish wasn't?"
- "What have you already tried to fix [primary pain area]?"
- [Any person-specific question based on Stage 2 research]

---

## What to Listen For
[2–3 sentences: what does a strong fit signal sound like in this conversation? What would tell JC this prospect is ready to move to a discovery session?]

---

## Red Flags
[Any context suggesting mismatch — wrong stage, wrong problem type, decision-maker not on the call, unlikely to act, etc. Write "None identified" if nothing stands out.]
```

---

## Widget Visual Pattern

- Outer card: `border: 0.5px solid var(--color-border-tertiary)`, `border-radius: var(--border-radius-lg)`, padding 1.5rem
- Section headers (The Company, The People, etc.): `font-size: 13px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.05em; color: var(--color-text-tertiary)`
- Anticipated Pains: numbered list, each item with a blue left border (`border-left: 2px solid #378ADD; padding-left: 10px`)
- Sharp Questions: bullet list, each item styled as a quoted question in a light background block (`background: var(--color-bg-secondary); border-radius: 4px; padding: 6px 10px; font-style: italic`)
- What to Listen For: green left border (`border-left: 2px solid #2E9E6B; padding-left: 10px`)
- Red Flags: orange left border (`border-left: 2px solid #E07B3A; padding-left: 10px`) — use grey if "None identified"
- "Copy as Markdown" button at bottom: `border: 0.5px solid var(--color-border-secondary)`, copies full brief as plain text
- All colors via CSS variables — never hardcoded except the accent borders above

---

## Output File

After rendering the widget, save the Call Brief as a markdown file to the vault at:

```
business/projects/[company-name-slug]/YYYY-MM-DD-call-brief-[company-name-slug].md
```

Use today's date and a lowercase-hyphenated version of the company name for the slug. Create the directory if it doesn't exist. Confirm to JC where the file was saved.

---

## Quality Check (run before rendering)

- [ ] All three required inputs were confirmed before research started
- [ ] Company website was fetched, not just searched
- [ ] Each person has title, tenure, background, and frame noted
- [ ] Anticipated pains are specific — no vague categories
- [ ] Each anticipated pain has a corresponding sharp question
- [ ] "What to Listen For" describes a concrete signal, not a generic fit criterion
- [ ] Red Flags section is populated or explicitly marked "None identified"
- [ ] Widget is rendered and "Copy as Markdown" button is included
- [ ] File is saved to `business/projects/` and path is confirmed to JC
