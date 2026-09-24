---
title: "Capital Financing — AI & Automation Opportunity Map"
date: 2026-09-10
tags: [client, deliverable, final]
status: final
---

# Capital Financing — AI & Automation Opportunity Map

## What this document is for

This maps where automation and AI can move the needle at Capital Financing, ranked by effort and impact.

It comes from eight weeks of discovery: process mapping across every department, plus direct conversations with the CEO, the DOO, the Servicing/AR Lead, and the Salesforce Administrator.

The value here isn't new discovery. It's turning eight weeks of calls and half-formed ideas into one ranked list. When a new idea comes up, check it against this list first. Score it the same way. Add it to the same map. That's how priority stays consistent instead of getting re-litigated every time.

**How to use it:** a new idea comes in. Check whether it's already here. If it is, fold it into the existing item. If it's new, score it with the framework below and add it to the map or the backlog. This keeps new ideas from turning into scope creep.

**What this isn't:** a build spec. This doesn't design exact tools or interfaces. It says where the highest-ROI opportunities sit and what kind of solution fits. Designing it comes next.

**What this doesn't cover yet:** this map leans toward intake, underwriting, and sales, because that's where discovery has gone deepest so far. The Servicing/AR Lead's Contracting, Funding, and Payouts process is mostly covered through Opportunity 6. The Controller's finance role isn't its own opportunity yet. That gap closes as those conversations continue.

---

## The Framework

Every opportunity gets scored on two axes and sorted into one tier.

**Effort:** Low, Medium, or High. Low means adoption or a small config change. Medium means a scoped build, measured in days. High means a multi-phase build, or one that depends on something else first.

**Impact:** Low, Medium, or High. This is the business value if it works: revenue protected, staff time freed up, or a real risk reduced, like a single point of failure or a compliance gap.

| Tier | Meaning |
|---|---|
| 🟢 **Quick Win** | Low effort. Ready now. |
| 🔵 **Near-Term** | A real build, scoped and sequenced after the quick wins. |
| 🟣 **Strategic** | High effort, high impact. Needs real design work. |
| ⚪ **Needs Decision First** | Not buildable yet. Blocked on a decision, missing information, or someone else's timeline. |

Effort and impact are scored in words here, not dollars. We don't have reliable time or cost numbers yet for most of this. Getting them, hours spent on manual servicing check-ins, cost per unfilled Opportunity record, is a real next step.

---

## Foundational note: the systems decision is made

Two opportunities below, Servicing Automation and Intake/Underwriting Structuring, sit on top of a decision that's already final. Salesforce stays the CRM and the system of record for automation and reporting. Segue is being adopted only for the roughly six ops and finance staff who need its financial features, with an integration bridging the two systems.

The case management system, Mighty/JB, is expected to migrate onto Segue over time. A good chunk of the manual servicing and AR work in Opportunity 6 should get absorbed by that migration. Not all of it will. See Opportunity 6 for what's left over.

### The priority right now: sales

Leadership's own priority, in writing: get the sales side supercharged first. The Financial Consultant pipeline, law firm follow-up, and referral conversion are the biggest lever available right now. Growth isn't capped by how many leads come in. It's capped by what happens after a lead lands: follow-up habits, KPI visibility, and consistent nurture.

Six opportunities on this map touch that pipeline directly: Opportunity 1, Opportunity 3, Opportunity 4, Opportunity 5, Opportunity 10, and Opportunity 13. Treat this group as the lead priority.

Opportunity 1 already started, in its simplest form. Consultants are bookmarking their account lists and logging every call and email starting now, and a basic volume report follows shortly after. Opportunity 3 is designed and ready, but it's sequenced after that foundation holds, not running in parallel with it.

If three more things move next, make them Opportunity 4 (referral-gap follow-up), Opportunity 10 (outreach automation), and Opportunity 12 (SharePoint architecture). All three are buildable now, independent of how Opportunity 1 and 3 play out.

Opportunity 2 (referral portal) is a fourth quick win worth running in parallel. It's low-risk and already scoped.

---

## A. The Opportunity Map

### Overview

```mermaid
flowchart LR
    classDef quickwin fill:#d1fae5,stroke:#059669,color:#065f46
    classDef nearterm fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    classDef strategic fill:#ede9fe,stroke:#7c3aed,color:#4c1d95
    classDef decision fill:#f3f4f6,stroke:#6b7280,color:#374151,stroke-dasharray: 4 3

    Ref[Referral Received] --> In[Intake Call and Docs]
    In --> UW[Underwriting]
    UW --> Ct[Contracting and Agreement]
    Ct --> Fd[Funding and Disbursement]
    Fd --> Sv[Servicing: AR, Payoffs, Close]

    Lead[Lead Assigned] --> Fol[Consultant Follow-Up]
    Fol --> Opp[Opportunity Tracked in CRM]
    Opp --> Ct

    Mkt[Outbound and Nurture] --> Lead

    In -.-> O1(["Structured intake +\nhard-rule auto-decline"])
    UW -.-> O1
    Ct -.-> O2(["Referral portal +\nfollow-up automation"])
    Sv -.-> O3(["Servicing findings feed\nSegue migration"])
    Fol -.-> O4(["CRM adoption:\nlogging habit first"])
    Opp -.-> O5(["Slack daily briefing:\ndesigned, sequenced next"])
    Mkt -.-> O6(["Outreach automation\nacross all channels"])

    class O1 strategic
    class O2 quickwin
    class O3 decision
    class O4 quickwin
    class O5 nearterm
    class O6 nearterm
```

### Priority summary

| # | Opportunity | Tier | Effort | Impact | Likely Owner |
|---|---|---|---|---|---|
| 1 | ⭐ Sales follow-up & pipeline adoption | 🟢 Quick Win | Low | High | Sales leadership + Salesforce Administrator |
| 2 | Referral/case-submission portal | 🟢 Quick Win | Low–Med | High | DOO's team |
| 3 | ⭐ Slack + exception-based digest | 🔵 Near-Term | Med | High | Salesforce Administrator |
| 4 | ⭐ Referral-gap detection & firm follow-up | 🔵 Near-Term | Med | High | Salesforce Administrator |
| 5 | ⭐ Salesforce → MailChimp sync | 🔵 Near-Term | Low–Med | Medium | Salesforce Administrator |
| 6 | Post-funding servicing/AR/payoffs, input to the Segue migration | ⚪ Needs Decision | — | High | Ops leadership |
| 7 | Intake & underwriting structuring | 🟣 Strategic | Med–High | High | DOO |
| 8 | Executive inbox AI assistant | 🟣 Strategic | Med–High | High | CEO + Blue Tusk |
| 9 | Internal staff FAQ assistant | 🟣 Strategic | Medium | Med–High | DOO + Blue Tusk |
| 10 | ⭐ Outbound outreach automation | 🔵 Near-Term | Medium | High | Sales leadership + Salesforce Administrator |
| 11 | Conference list matching & territory structure | ⚪ Needs Decision | High | Medium | CEO |
| 12 | SharePoint information architecture & adoption | 🟢 Quick Win | Low–Med | High | Blue Tusk (design) + DOO (rollout) |
| 13 | ⭐ Conference ROI tracking & pre/during/post cadence | 🔵 Near-Term | Medium | High | Salesforce Administrator |
| 14 | Website & SEO performance visibility | 🟢 Quick Win | Low–Med | Medium | Blue Tusk + CEO |

---

### 1. Sales follow-up & pipeline adoption — 🟢 Quick Win

**The pain:** Consultants aren't following up consistently, and nobody can see who's working what. Most of the fix already exists. Salesforce has a full Opportunity object built for this, with stages for case-expense and pre-settlement deals, plus automated tasks: a 7-day no-meeting trigger, a 30-day no-referral trigger. Nobody uses it, so it has no data to work with. Same story with the KPI dashboard. Built, reviewed once, left alone.

**The opportunity:** This starts even more basically than the Opportunity pipeline. Right now, most calls and emails aren't logged as activity at all, so there's no data for anything downstream, including Opportunity records, to work with. The sequence has to go in order: log every call and email first, then create Opportunity records once real positive responses start coming in, then turn the KPI dashboard back on once there's enough real data to make it meaningful.

The metrics to track are no longer a guess. Howie's own FC training materials name them directly: total referred revenue against goal, total volume of advances referred, new law firm accounts added, Strategy Calls completed, Case Expense Onboarding Calls completed, and time to first funding on new accounts. Commission only counts law-firm-referred business, not a returning client who self-initiates a new loan, so any automation needs that filter built in from the start.

**Status: phase one is rolling out now.** Every consultant is being asked to bookmark three Salesforce views (active accounts, inactive accounts, prospects) and log every call and email as an activity at the time it happens, for every contact, no exceptions. A one-page training document covers this alone. Once that habit holds, the Salesforce Administrator will add a simple report showing raw call and email volume per consultant per day, including leadership's own volume as a benchmark. Opportunity-record creation and the KPI dashboard come after this foundation is real, not before.

```mermaid
flowchart LR
    classDef quickwin fill:#d1fae5,stroke:#059669,color:#065f46
    A[Lead Assigned] --> B[Consultant Follow-Up]
    B --> C[Opportunity Record Created]
    C --> D[Auto Task / Notification Logic]
    D --> E[Outcome Logged]
    B -.->|starting now| Opp2(["Log every call and\nemail as an activity"])
    C -.->|next, once logging is real| Opp1(["Create Opportunity records\nfrom positive responses"])
    class Opp1 quickwin
    class Opp2 quickwin
```

*Solution shape:* Training and a habit change first. A simple volume report next. Opportunity-record adoption and the KPI dashboard follow once the basic logging habit is real.

---

### 2. Referral/case-submission portal — 🟢 Quick Win

**The pain:** Firms submit case documents through a Word doc. Leadership has called it "unappealing, overwhelming, and unprofessional." That's the CEO's own top reason for lost business.

**The opportunity:** Replace the Word doc with a branded, firm-specific web form. One link per firm, with validation, document upload, and automatic notifications. Already in motion with the DOO's team, low-risk and low-cost.

```mermaid
flowchart LR
    classDef quickwin fill:#d1fae5,stroke:#059669,color:#065f46
    A[Onboarding Call Complete] --> B["Follow-up email,\n6 attachments, Word doc"]
    B --> C[Firm fills out & emails back]
    C --> D[Manual re-entry into CRM]
    B -.->|replace| Opp1(["Branded web form\n+ installable app"])
    class Opp1 quickwin
```

*Solution shape:* A form tool, already chosen. Installable as a lightweight app later, so firm staff don't lose the link.

---

### 3. Slack + exception-based digest — 🔵 Near-Term

**The pain:** The company already has close to a hundred Salesforce reports and dashboards. There's no single, obvious place that points anyone toward them day to day, so they go unused even when they'd answer the exact question someone's asking. The Slack subscription is already bought.

**The opportunity:** A daily briefing in Slack, at the start of each consultant's day, split into three tiers: opportunities that need attention first, high-priority new contacts next (conference attendees, for example), and lower-priority new contacts after that. Click through from Slack straight into the record, log the interaction there, and never open Salesforce at all. At the end of the day, leadership gets an automated report in Slack showing how many calls, emails, and in-person visits each consultant made. Nothing to search for.

**Status: designed, not yet started.** This system was designed in a working session with the Salesforce Administrator, and the mechanics are real: a three-tier daily list, one-click logging, an automated end-of-day report, time-based follow-up reminders keyed to how long it's been since the last contact. But it depends entirely on the basic logging habit in Opportunity 1 being established first. Building this on top of today's data would mean building it on top of almost nothing. The realistic sequence: get consultants logging consistently, watch the simple volume report for a few weeks, then build this system on data that's actually there.

Two more pieces came up in the same design session, further out still. An AI-generated account summary a consultant could pull up in Slack before an in-person visit, once this system itself is running. And a telephony system that would auto-transcribe and auto-log calls, which becomes a much easier case to make once there's real call-volume data to point at.

```mermaid
flowchart LR
    classDef nearterm fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    A[Start of Day] --> B["Daily Priority List\nin Slack"]
    B --> C["Opportunities\nNeeding Attention"]
    B --> D["High-Priority\nNew Contacts"]
    B --> E["Lower-Priority\nNew Contacts"]
    C --> F["Log Interaction\nin Slack"]
    D --> F
    E --> F
    F --> G["End-of-Day Report\nto Leadership"]
    class B nearterm
    class G nearterm
```

*Solution shape:* Already scoped. A Slack-based daily briefing and an automated end-of-day report, both reading from Salesforce data. Sequenced to start once Opportunity 1's basic logging habit is established, not before.

---

### 4. Referral-gap detection & automated firm follow-up — 🔵 Near-Term

**The pain:** A firm signs on, gets excited, and then never sends a case. Or sends one and goes quiet. Nothing catches this today.

**The opportunity:** A defined follow-up sequence keyed off CRM timestamps: last referral, last call, last email. Automatic escalation if a firm goes cold, instead of relying on someone remembering to check.

```mermaid
flowchart LR
    classDef nearterm fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    A[Firm Onboarded] --> B["Manual follow-up,\nif it happens"]
    B --> C[Weeks pass, no referral]
    C --> D[Firm goes quiet]
    B -.-> Opp1(["Automated multi-touch\nsequence + escalation"])
    C -.-> Opp1
    class Opp1 nearterm
```

*Solution shape:* An extension of the same automation pattern built for Opportunity 1. Timestamp-triggered tasks and templated touches. No new architecture needed.

---

### 5. Salesforce → MailChimp sync — 🔵 Near-Term

**The pain:** Warm marketing runs through MailChimp now, but getting a current contact list there is a manual monthly export and upload from Salesforce.

**The opportunity:** Automate the sync so it doesn't depend on someone remembering to run it. Keep the active, inactive, and prospect tags intact on the MailChimp side.

*Solution shape:* A scheduled export or a direct sync between the two systems. One direction only. No new segmentation logic needed.

---

### 6. Post-funding servicing/AR/payoffs, input to the Segue migration — ⚪ Needs Decision First

**The pain:** Staff spend real time on manual check-in emails to law firms, just to track a case toward settlement. Both the CEO and the DOO have called this function ready for automation.

**This is a migration-scoping item, not a build.** A good chunk of this should be handled by the planned migration off the current case-management system onto Segue. Not all of it will be. Rather than scope this as new development, here's what's worth carrying into that migration conversation, so it doesn't get lost in a generic "modernize the system" discussion.

**Weaknesses to carry into the Segue transition:**
- No automated reminders exist today. Follow-up is fully manual.
- Cadence is discretionary. It varies by staff member and by firm relationship, with nothing written down.
- Multiple staff members do overlapping manual check-ins that one system could consolidate.
- The case system and the financial system reconcile today through a manual name match, not a shared case ID. Confirm whether Segue solves this natively, or whether the same manual match survives the migration.

```mermaid
flowchart LR
    classDef decision fill:#f3f4f6,stroke:#6b7280,color:#374151,stroke-dasharray: 4 3
    A[Funded Case] --> B["AR Tracking\n(manual check-ins)"]
    B --> C[Payoff / Reduction Request]
    C --> D[Deposit Received]
    D --> E[Reconciled & Closed]
    B -.->|"multiple staff,\nmanual status-check emails"| Opp1(["Findings feed the\nSegue migration requirements"])
    class Opp1 decision
```

*Solution shape:* Not a build. A requirements list for the Segue migration conversation. Revisit this as a real opportunity once the migration's scope and timeline are set, since whatever it doesn't cover is the actual remaining work.

---

### 7. Intake & underwriting structuring — 🟣 Strategic

**The pain:** Underwriting runs on two layers: a rules layer (state law, case type, eligibility) and a judgment layer (attorney reputation, gut read). Today every case reaches the DOO for review, no matter which layer it actually needs. This is also the biggest blocker to the Segue build, which needs the intake questionnaire structured before it can be customized.

**The opportunity:** Structure the rules layer into a defined questionnaire with hard checkpoints. A case that clearly fails never reaches the DOO. That frees up time for the judgment calls only that role can make.

```mermaid
flowchart LR
    classDef strategic fill:#ede9fe,stroke:#7c3aed,color:#4c1d95
    A[Client Interview] --> B[Case Facts Gathered]
    B --> C[Underwriting Review]
    C --> D{Rules Pass?}
    D -- No --> E["Still routes to the DOO\ntoday, every time"]
    D -- Yes --> F["Judgment / gut call\n(the DOO's real value)"]
    D -.-> Opp1(["Structured questionnaire\n+ hard-rule auto-decline"])
    class Opp1 strategic
```

*Solution shape:* A decision-tree intake questionnaire, for both clients and law firms, feeding a rules engine. Not a full underwriting AI. The judgment layer stays human by design. Gated on the underlying intake and underwriting content actually getting written down.

---

### 8. Executive inbox AI assistant — 🟣 Strategic

**The pain:** The CEO personally handles 200 to 300 emails a day. A real share of them shouldn't land there at all: staff and HR questions that belong with the DOO, case intake that belongs with the team. The rest is low-value overhead, like redundant status reports and approval loops that repeat themselves.

**The opportunity:** Already fully specified by the CEO. A triage layer that suggests instead of auto-forwarding, draft-shortening help, and flags on emails aging without a response. Works inside the existing inbox. No folders, no rules. That's a hard constraint.

*Solution shape:* An inline, suggestion-based assistant on Outlook. Not an auto-sort system. That's already been ruled out.

---

### 9. Internal staff FAQ assistant — 🟣 Strategic

**The pain:** Standard staff questions, like the PTO process or intake procedure, go straight to the DOO or the CEO, or get lost in a disorganized SharePoint. Both have proposed the same fix independently.

**The opportunity:** A Q&A layer that answers from the company's actual documentation, with SharePoint staying underneath as the source of truth.

*Solution shape:* Straightforward once the content exists. Gated on the DOO's SOPs and FAQ material actually getting written. Not a technical blocker.

---

### 10. Outbound outreach automation — 🔵 Near-Term ⭐

**The pain:** Prospecting, reactivation, thank-you emails, active-account nurture, post-conference follow-up, and the long-term law firm drip series all run manually today, mostly through one person. Reactivation emails aren't getting results. Active accounts get no nurture at all. Thank-you emails go out by hand after every new referral. None of it is consistent, and one person's bandwidth caps how much of it happens.

**The opportunity:** Leadership has already called for this to move to AI-assisted, better-automated email generation and sequencing across all six of those motions. The direction is set. What's left is deciding the tool and the team structure around it, not whether to do it.

*Solution shape:* A sequencing and generation layer across the existing law firm segments (prospect, active, inactive), built on top of the Mailchimp migration already underway. Scope the six email motions as one system, not six separate fixes.

---

### 11. Conference list matching & territory structure — ⚪ Needs Decision First

**The pain:** Matching new conference contacts against roughly 25,000 existing Salesforce contacts takes about two hours per list by hand, with only half auto-matching. Assignment to consultants is manual too, and untracked.

**The opportunity:** Automate the matching and the assignment. But assignment logic depends on defined consultant territories first, which is an org and economics decision, not a technical one.

*Solution shape:* Not scoped until the territory question is settled.

---

### 12. SharePoint information architecture & adoption — 🟢 Quick Win

**The pain:** File organization across the company is a real problem, and it isn't about which tool people prefer. Sensitive documents, like bank reporting, reach the CEO only through one-off email attachments, with no shared access at all. Different teams default to different systems out of habit. Even where SharePoint is already in use, there's no consistent folder structure or naming convention, so it's hard to trust or navigate.

**The opportunity:** This one's decided. SharePoint is the company-wide system going forward. What's left is the actual architecture: a folder taxonomy, naming conventions, governance rules, and a real migration push to get everyone onto one structure. This is scoped as foundational on purpose, not a full automation build. It's the base every future document-facing automation needs, including the staff FAQ assistant in Opportunity 9, or a future connection between Claude and the company's documents for search, summary, or drafting. That connector work is a natural next phase once the taxonomy exists. It's not something to build before the foundation is there.

*Solution shape:* An information architecture project: taxonomy design, migration, adoption habits. Not a software build. Simple and contained relative to everything else here, which is exactly why it's a fast, visible win.

---

### 13. Conference ROI tracking & pre/during/post cadence — 🔵 Near-Term ⭐

**The pain:** Capital Financing attends 15 to 20 conferences a year at real cost. There's no reliable way to trace a referral back to the conference contact that generated it. Attendee lists come from organizers as name, phone, and address only, no email, which makes the follow-up chain harder to hold together. The consultant team hasn't reliably run post-conference follow-up on their own, which is part of why this work slipped to outside help in the first place.

**The opportunity:** The Salesforce Administrator is already building attendee-level reporting. That's the foundation. Layer a defined pre-conference, during-conference, and post-conference touch sequence on top of it, tied to Mailchimp, with attribution back to the originating conference so ROI is visible for the first time. Conference attendees are also the model example for the "high-priority new contacts" tier in the Opportunity 3 daily briefing, so this and Opportunity 3 should be built with the same contact-prioritization logic in mind.

*Solution shape:* A cadence system similar to Opportunity 4, keyed to conference attendance instead of firm onboarding. Attribution reporting sits on top of the tracking the Salesforce Administrator already has in motion.

---

### 14. Website & SEO performance visibility — 🟢 Quick Win

**The pain:** SEO is fully outsourced and has been for years. Monthly reports come back, but they're hard to read, and there's no independent way to check whether the work is actually moving rankings, traffic, or conversions. Meetings with the vendor are rare.

**The opportunity:** A simple, automated performance view pulling from Google Analytics, Search Console, and rank tracking, so performance is visible without depending on the vendor's own narrative.

*Solution shape:* A scheduled report or lightweight dashboard on top of tools that already exist. No new SEO work required, just visibility into what's already running.

---

## B. Quick Wins (ready to move on now)

Quick wins are a possibility surfaced by discovery, not a promise. These three actually clear that bar.

1. **Sales follow-up & pipeline adoption (Opportunity 1).** No new build. Turn on and enforce automation that's already paid for and built. The single highest-leverage move on this map.
2. **Referral/case-submission portal (Opportunity 2).** Already scoped and in motion with the DOO's team, on a low-risk, low-cost tool. Needs a check-in to confirm it's moving, not a new decision.
3. **SharePoint information architecture & adoption (Opportunity 12).** No build required. Taxonomy design plus a real rollout push. A strong, low-risk opener for a follow-on engagement: contained, visible, and the foundation several other opportunities here will eventually need.

Everything else on this map is a real build or a pending decision. Sequencing them is the next conversation, not a promise to make before they're scoped.

---

## C. How new ideas get added

1. **Check if it's already here.** Most new ideas map onto one of the fourteen opportunities above, sometimes as a new detail on an existing one rather than something new.
2. **If it's genuinely new, score it.** Effort: Low, Medium, High. Impact: Low, Medium, High. Same definitions as the framework above.
3. **Tier it.** Quick Win, Near-Term, Strategic, or Needs Decision First.
4. **Add it to the backlog below,** with its source and date. It only moves onto the main map once it's scoped enough to sit next to the other fourteen. A one-line idea doesn't jump straight to the priority table.

This is what keeps new ideas from turning into scope creep. Everything gets measured the same way, in one place, instead of each idea getting its own conversation about whether it matters.

---

## D. Financial Consultant Workflow: a shell to fill in first

You asked whether it would help to interview the Financial Consultants and map their actual day-to-day workflow. It would, eventually. Not yet, for two reasons.

The FC workflow is about to change. The CRM adoption push in Opportunity 1, the Slack digest in Opportunity 3, and the referral-gap automation in Opportunity 4 will all touch how a consultant spends a day. Mapping the workflow now means mapping something that's already changing.

The bigger reason: automation needs real activity data to point at, and that data doesn't exist yet in a usable form. General categories of sales automation can be named now. Specific recommendations, the kind worth actually building, need to wait until consultants are tracking their own actions consistently.

What's below is a shell, not a finished map. It lays out the sequence of activity a consultant works through, with the kind of automation that typically fits at each step once real tracking exists. Fill in what actually happens today at each step, and where it's currently logged, if anywhere. That's the input the next round of automation recommendations needs.

```mermaid
flowchart LR
    classDef quickwin fill:#d1fae5,stroke:#059669,color:#065f46
    classDef nearterm fill:#dbeafe,stroke:#2563eb,color:#1e3a8a

    A[Source or Receive Leads] --> B[Clean the List]
    B --> C[Research Leads]
    C --> D[Write Script or Email]
    D --> E[Call or Email Leads]
    E --> F[Follow Up]
    F --> G["Move Interested Prospects\nThrough the Sales Process"]
    G --> H[Log the Action]

    A -.-> P1(["Dedup +\nassignment rules"])
    C -.-> P2(["AI screening against\na defined firm profile"])
    D -.-> P3(["AI-assisted drafting\nfrom set templates"])
    F -.-> P4(["Designed, sequenced after\nOpportunity 1 (Opportunity 3)"])
    G -.-> P5(["Designed, sequenced after\nOpportunity 1 (Opportunity 3)"])
    H -.-> P6(["Starting now\n(Opportunity 1)"])

    class P1 nearterm
    class P2 nearterm
    class P3 nearterm
    class P4 nearterm
    class P5 nearterm
    class P6 quickwin
```

Two steps worth calling out directly.

**Calling and emailing itself isn't the automation target.** That's the relationship-building core of the role. The right tool speeds up getting to the call, not the call itself. Research and script writing on one side, follow-up and logging on the other, are where automation actually helps.

**Logging is the step you already named as the real blocker, and the fix is starting now.** Consultants weren't selecting the right follow-up fields after a call, and the CRM already had fields built for exactly this. The immediate fix, see Opportunity 1, is the simplest possible version: log every call and email as it happens, starting today. The fuller version, moving logging into Slack with one click from a daily priority list, is designed and ready (Opportunity 3), sequenced right after this foundation holds.

**What's genuinely out of scope here:** writing the SOPs, running the training, and managing the behavior change with the Financial Consultants. A one-page training document for the immediate logging habit is ready now (Opportunity 1). The fuller SOP for the Slack system comes once that build actually starts (Opportunity 3). Running the training itself and managing the ongoing behavior change isn't part of this engagement. This shell is the input for the steps that still need it (sourcing, cleaning, researching, and writing to leads), not a replacement for that work.

---

## Appendix: Full Backlog

Everything tracked that isn't on the curated map above, either too early-stage to score with confidence, or minor enough not to need a headline slot.

| Item | Tier | Note |
|---|---|---|
| AI-readable LinkedIn/Facebook bio | 🟢 Quick Win (minor) | Zero-build housekeeping. A prompt leadership can run directly. |
| Move training videos off Vimeo | 🟢 Quick Win (minor) | File migration and reorg. No technical build. |
| Team-wide AI notetaker | 🟢 Quick Win (minor) | Tool selection and rollout. Adoption is the real work, not the tool. |
| Outreach contractor repositioned as personal assistant | ⚪ Needs Decision | Now easier to resolve since Opportunity 10 answers the automate-or-retire question. This is the remaining piece: what the person does once the email work is automated. |
| KPI dashboard improve-vs-leave-as-is call | ⚪ Needs Decision | Needs a direct review with the Salesforce Administrator before recommending either way. |
| Consultant dashboard / weekly reporting layer | 🔵 Near-Term | Downstream of Opportunity 4 (referral-gap detection). Sequence after, not before. |
| Territory-based FC structure | ⚪ Needs Decision | Org and economics decision. Blocks Opportunity 11. |
| Commissions-spreadsheet automation | 🔵 Near-Term | Overlaps with Opportunity 1. Scope together once CRM adoption is underway. |
| Segue/Salesforce hybrid architecture | — | Already decided. See Foundational Note above. Not a ranked opportunity. |
| State/regulatory registration renewal tracker | 🟢 Quick Win (minor) | Small, contained tracking need for litigation-funding state registrations and annual renewals. Currently an ad hoc spreadsheet just started. Low effort, modest impact, but genuinely useful. |
