# Ruthless For Good Fund

Early-stage venture fund (education, work, and access focus) transitioning from Fund I to a Fund II raise, currently building out back-office infrastructure before officially launching the raise.

**Primary contact:** Aaron Walker, Founder & Managing Partner — aaron@ruthlessforgood.com

## Changelog

### 2026-08-18 — Martina's comments on AI Playbook draft
- **Gripe list (Playbook §1):** Confirmed all three team members (Aaron, Michael, Martina) use Notion. Martina already has a gripe list set up there, feeding into the weekly team agenda — the playbook builds on this existing list rather than a new one.
- **Tools that act (Playbook §4):** Martina confirmed as RFG's Claude admin. Cowork believed toggled off org-wide (she'll confirm directly once logged into a slow-loading admin session). Twintel's tenant-permission review is complete. Both Cowork and Claude Code are off.
- **Where data goes (Playbook §7):** RFG is on a Claude **Team plan with 3 seats**.
- **Who runs this (Playbook §9):** Confirmed as **Martina + Barry** — matches the proposal already logged in the Action Plan (Martina day-to-day, Barry on tool/permission-specific items).

### 2026-08-18 — Email exchange (JC ↔ Martina, post-Meeting 2)
- JC sent post-meeting recap naming fundraising CRM as the primary need and deal-flow analysis as secondary (goal: move RFG from reactive/passive deal intake to proactive, thesis-driven investing informed by inbound data).
- JC proactively raised a second opportunity: structuring shared drives/filesystems (Google Drive, SharePoint, etc.) properly from the start, since messy drives create AI "waste" and cause AI to miss or misidentify information — easier to do right from day one than to untangle later.
- **Decision — scope narrowed:** Aaron, Caroline, and Martina aligned on starting narrow: AI-assisted triage of **Aaron's inbox and calendar** (his actual bottleneck) first, and letting that feed the CRM organically rather than building the CRM cold. This supersedes the original plan to start with a live/async CRM requirements-discovery session — see Action Plan.
- **Decision — governance is now a hard gate:** RFG's one condition before widening tool access is getting the AI governance document in place first; they'll review it to get comfortable turning on Claude Cowork. This elevates P-003 from "nice to have soon" to a blocking dependency.
- **New technical constraint surfaced:** RFG's mail lives in **Microsoft 365/Outlook**, not Gmail — Claude reads Gmail natively but not Exchange. A Claude for Outlook add-in exists; Martina is checking tenant permissions with **Twintel** (their IT vendor). Open question for JC: cleanest way to run an inbox assistant on this setup.
- **Shared-drive point confirmed as good timing:** RFG deliberately migrated to SharePoint "as-is" and held off on restructuring, intentionally saving that work for **Fund II data-room prep** — so JC's proactive suggestion lines up with a restructure they already knew was coming. Martina asked JC to spell out what "doing it right from the start" would involve on RFG's side and what oversight looks like on Blue Tusk's side.
- **Decision authority confirmed:** Aaron holds the final call on how the engagement proceeds; Martina is bringing all of the above to him.
- **Owed by JC next:** (1) send the AI governance document, (2) give a recommendation on the cleanest way to run an inbox/calendar assistant against Outlook/M365, (3) outline what a proper shared-drive/SharePoint restructure would involve and what oversight it requires from Blue Tusk.

---

## 1. Client and Organization

- **Entity:** Ruthless For Good Fund — early-stage venture fund.
- **Focus areas:** Education, work, and access.
- **Principal:** Aaron Walker, Founder & Managing Partner (aaron@ruthlessforgood.com). Background: teacher → lawyer → ran an accelerator → founded Ruthless For Good. Based in Madison, Wisconsin (East Coast transplant).
- **Team size:** Intentionally lean — two core investing staff (Aaron and Michael), plus fractional/outsourced support.
- **Fund history:** Fund I raised 2021–2022 (~$20M), fully invested. Now preparing to raise Fund II, targeting ~$50M.
- **Headquarters:** 11484 Alps Way, Escondido, CA 92026. Main phone: (951) 294-4574.

---

## 2. Business Profile

Ruthless For Good is a two-person (Aaron + Michael) early-stage venture fund investing in companies focused on education, work, and access. Fund I closed at roughly $20M in 2021–2022 and is now fully deployed; the organization's current mode is preparation, not active investing — getting operational, governance, and technology infrastructure in order ahead of an official Fund II launch. Aaron characterizes the timing as "important but not urgent": no external deadline is forcing action, but the team wants "their house in order" before the raise formally kicks off next year. Fundraising for Fund II is expected to take 18–24 months once launched.

The organization is early-stage and scrappy by design — lean intentionally, both to stay economical and to stay manageable at the current asset scale. A large amount of institutional knowledge (investor relationships, deal history, process) currently lives only in Aaron's head or in ad hoc tools (text messages, email, memory), rather than in a shared system. Martina (fractional ops) has been engaged roughly six weeks at the time of the first call, working through foundational cleanup: a business insurance application, budget/finance review, and an initial look at the fund's Notion-based CRM. Barry was separately brought on to provide IT governance and cybersecurity guidance, introduced via a mutual connection with Martina.

The engagement originated as a referral from Barry and Martina, who had previously worked with Blue Tusk on a comparable engagement for another client ("MakeHome"), including an AI usage/governance framework Blue Tusk is prepared to adapt for Ruthless For Good.

Two work areas exist inside the fund, distinct in urgency and ownership:
- **Deal flow / inbound pipeline** — pitches, sourcing, vetting. Currently secondary in priority since there's no capital to deploy yet, but the team wants it running concurrently so the pipeline stays warm and so market/trend signal from inbound pitches isn't lost. Framed explicitly (per JC's 2026-08-18 recap) as moving RFG from *reactive/passive* deal intake to *proactive, thesis-driven* investing informed by inbound data. This work will primarily belong to Michael and any future investment team, not Aaron personally.
- **Investor relationships / fundraising** — the relationship-management work behind raising Fund II. Currently owned almost entirely by Aaron, tracked informally across his memory, text messages, and email. Considered higher-stakes and more personal. Confirmed (2026-08-18) as RFG's primary need and Aaron's core differentiator — the actual near-term entry point is narrower than a full CRM rebuild: AI-assisted triage of Aaron's inbox and calendar, feeding the CRM as a byproduct rather than requiring the CRM to be built cold first.

---

## 3. Goals

**Personal Goals**
- Aaron wants to spend his time on relationship-building and investor conversations ("coffee chats") — the highest-value use of his time as a solo relationship-holder for the fund — rather than administrative/back-office work like insurance applications or manual data entry.
- Reduce the degree to which fund knowledge and relationships live only in Aaron's head; build something that doesn't depend entirely on his memory.

**Business Goals**
- Successfully raise Fund II at ~$50M (more than double Fund I's ~$20M), which Aaron frames as requiring the fund to "not just barely get to 20" again — i.e., a step change in process discipline, not just more hustle.
- Build an institutional CRM/data system that belongs to Ruthless For Good, not to any one person (Aaron or Michael individually), so relationships and deal history survive staff transitions and can eventually be delegated.
- Get better visibility into what inbound deal flow is signaling about market trends and opportunities, even while deal-making itself is paused.
- Put AI governance in place (a written usage framework) before enabling more autonomous AI capabilities (Claude's "co-work"/agentic features, Notion's agents), consistent with cybersecurity/governance being built out by Barry.

---

## 4. Key People — Internal

**Aaron Walker** — Founder & Managing Partner — aaron@ruthlessforgood.com
- Working Style: Direct, self-aware about gaps ("I don't think I need to have a first deliverable next week... but it's important"). Comfortable naming that his own systems (relationships tracked in his head, texts, and email) don't scale. Values efficiency and plain talk about cost/timing — asked directly what a paid engagement would cost.
- Owns fundraising, investor relationships, and overall firm management. Has raised one prior fund (2021–2022) and ran a nonprofit for 10 years before this, so brings existing relationship capital plus fundraising experience.
- Traveling internationally for two weeks starting the week after the second call — a known near-term availability gap.
- Relevance: Primary decision-maker and champion for the engagement; final approval on the free-MSA structure had to route through him.

**Michael Ladipo** — Vice President — michael@ruthlessforgood.com
- With the fund since November 2021 (since it started investing).
- Owns deal sourcing, vetting, and portfolio support.
- Uses Claude in his work already, but — per Barry and Martina — without a clear sense of the risks or guidelines around it.
- Was on parental leave at the time of the second call and was not present; Aaron spoke on his behalf.
- Relevance: Will be the primary owner of the rebuilt deal-flow/CRM system going forward; a key stakeholder for the CRM rebuild even though not yet directly consulted.

**Martina Madrid Sebring** — Fractional Operations (Madrid Ops) — martina@madridops.com (fractional COO company email), martina@ruthlessforgood.com
- Working Style: Hands-on and embedded in the day-to-day, in contrast to Barry who stays outside the company's technology environment by design.
- Has been engaged roughly six weeks as of the first call. Currently working the business insurance application, budget/finance support, and an initial CRM review.
- Confirmed (2026-08-18): holds RFG's Claude admin seat, and is confirmed — jointly with Barry — as the point of contact for AI-tool "is this okay to try" questions (Playbook §9).
- Relevance: Primary internal driver connecting Blue Tusk to the fund; likely the ongoing operational point of contact for this engagement day-to-day.

---

## 5. Key People — External (Vendors & Partners)

**Barry Porozni** — IT Governance & Cybersecurity Advisor — barry@porozni.com
- Brought on to provide IT governance and cybersecurity guidance to Ruthless For Good, introduced through a mutual connection with Martina.
- Stays intentionally outside the fund's actual technology environment/tenant — advises from a process and governance perspective at designated check-in points rather than working inside day-to-day systems.
- Confirmed (2026-08-18): jointly with Martina, holds the "who runs this" role for AI tool questions (Playbook §9) — specifically on tool/permission-related items.
- Relevance: Referral source for the Blue Tusk engagement (also referred Blue Tusk to a prior client, "MakeHome"); a governance stakeholder whose cybersecurity work should stay coordinated with any AI-agent rollout (Claude co-work, Notion agents).

**Caroline Rosch-Hoover** — Advisor to Ruthless For Good — caroline@worthyendeavors.net
- Background: Reinvestment Fund (fundraising, fund operations, portfolio management — same firm where she first met John-Carlos and Barry, in Philadelphia), then COO of Grounded Capital (California) for ~4 years, including a fund-transition (Fund I → Fund II) there.
- Has been advising Aaron and Martina for the past few months.
- Explicitly stays outside the fund's technology/data systems day-to-day; joined this call out of curiosity about the engagement's direction rather than as a hands-on operator.
- Relevance: Advisor with directly relevant fund-transition experience (having lived through a comparable Fund I→II transition at Grounded Capital); useful sounding board but not an implementation stakeholder.

**Twintel** — IT Vendor (tenant/permissions management)
- Managing RFG's Microsoft 365 tenant; being consulted by Martina on tenant permissions needed to run a Claude-based inbox assistant against Outlook/Exchange.
- Relevance: Technical gatekeeper for the inbox/calendar triage workstream — permissions need to clear through them before that build can start.
> ⚠️ NEEDS INPUT: Twintel contact name/details; status of the tenant-permissions check.

**John-Carlos / Blue Tusk LLC** — AI & Automation Consulting (Blue Tusk's own engagement)
- Proposed structure: free engagement to start, governed by a free MSA covering confidentiality for anything discussed about the business. No fixed time limit on the free phase — continues as long as no proven value has been delivered yet, expected to run ~1–2 months minimum.
- Pricing signaled (not yet contracted): first invoice ballpark ~$2,000, ramping toward ~$5,000/month at peak build-out/coordination load, then settling back down to roughly half or a quarter of the peak fee once tooling and workflows are running and easier to maintain.
- Immediate scope offered at no cost regardless of paid-engagement decision: an AI usage/governance document (Claude guidelines), adapted from a template already built for another client ("MakeHome"), scaled down for a 2-person team.
- Pending decision: Aaron needs to align internally (via the team's weekly meeting) and confirm he wants to proceed under this free-to-paid structure before deeper engagement begins.

---

## 6. Technology Stack

**Notion** — Primary system of record, used company-wide.
- Currently on a paid Notion "Teams" plan.
- Confirmed (2026-08-18): all three team members (Aaron, Michael, Martina) use Notion. Martina maintains a gripe list there that already feeds into the weekly team agenda — identified as the base for the AI Playbook's gripe-list habit rather than a new list.
- CRM: Built from a purchased third-party Notion CRM template (~$100), not fully explored or configured. Requires significant manual data entry and is not well linked across databases — described by Aaron as still needing heavy setup work.
- Note-taking: Not yet using Notion's built-in meeting note-taker; Aaron has tried Fireflies and Read AI in the past and dislikes tools that visibly join the call. Considering switching to Notion's native note-taker instead.
- AI agents: Notion offers autonomous agent capabilities the fund has not yet adopted; Aaron flagged concern (prompted by a related internal discussion about Claude's co-work risks) about whether Notion's agents carry similar risk.
- Current state: heavily fragmented — multiple small, personal databases rather than one connected system — which limits how well AI tools can reason across the fund's data.

**Claude** — AI assistant, adopted April [2026, inferred from "we got Claude for the first time in April"].
- Used by Aaron and Michael in their individual work.
- Co-work / autonomous-agent features intentionally **not** enabled yet — the team is holding off until an AI governance program is in place.
- Confirmed (2026-08-18): RFG is on a **Team plan with 3 seats**. **Martina holds the admin seat.** Both Cowork and Claude Code are toggled off org-wide (Martina confirming directly once logged into a slow-loading admin session, but that's her expectation).
- Team has had light exposure to AI concepts via workshops/consulting offered by some of the fund's own investors, but has not implemented structured skills or workflows.

**Microsoft 365 / Outlook** — Email and calendar, primary bottleneck for Aaron.
- RFG's mail and calendar run on Microsoft 365/Exchange, not Gmail. Claude reads Gmail natively but not Exchange; a Claude for Outlook add-in exists as a possible path.
- Confirmed (2026-08-18) as the actual first build target: AI-assisted triage of Aaron's inbox and calendar, ahead of any CRM work.
- Tenant permissions being checked by Martina with Twintel (RFG's IT vendor). **Confirmed (2026-08-18): the tenant-permission review is complete** — clears one of the two blockers on the inbox/calendar triage workstream (the other being sign-off on the AI Playbook/governance doc).

**SharePoint** — Shared drive / document storage.
- RFG migrated to SharePoint "as-is" when they moved, deliberately deferring any real restructuring.
- Real restructure intentionally saved for **Fund II data-room prep**, so JC's proactive suggestion (structure it properly before AI reads it, to avoid AI "waste" and missed/misidentified information) lines up with work RFG already knew was coming.
- Pending: JC to outline what "doing it right from the start" involves for RFG and what oversight it requires from Blue Tusk.

**Web intake form** — Not yet built.
- No form currently exists for accepting inbound pitches/decks on the fund's website.
- Identified as a near-term opportunity: a form that could route submissions into an automated flagging/categorization pipeline against investment criteria.

> ⚠️ NEEDS INPUT: Financial/accounting software currently in use (referenced budget/finance work with Martina, but no specific tool named). Business insurance vendor/status — confirmed unknown/not yet determined as of the last check-in.

---

## 7. Problem Register

### P-001 — CRM is fragmented and manual
- **Area:** Systems / Processes
- **Problem:** The fund's Notion CRM is built from an unconfigured purchased template. It requires heavy manual data entry, isn't meaningfully linked to other data (contacts, deals, projects), and currently lives across scattered personal databases rather than one connected system. This makes it hard for both people and AI tools to get a full picture, and data entry currently has no clear payoff ("I put it there and then I'm never going to look at it again").
- **Current Thinking:** The team treats data entry as a chore disconnected from any future benefit, and treats the CRM as something to eventually "fill out" rather than something to design around actual use.
- **Reframe:** Data entry should feel worthwhile because the system immediately does something useful with it — a live daily dashboard, a next-touch prompt, a suggested follow-up message — not just an inert record.
- **Approach:** Rebuild as a single master Notion database with tagged views (e.g., investor vs. company vs. deal) so AI tools can reason across one connected dataset instead of many disconnected ones. **Updated 2026-08-18:** RFG wants to start with inbox/calendar triage rather than a full CRM build, but that doesn't remove the need for structure entirely — feeding an AI assistant into an unstructured CRM just produces unstructured AI output faster. JC's read: a **light, upfront pass at minimum CRM structure** (the core fields and views, not the full buildout) needs to happen alongside or just ahead of the inbox/calendar workstream, so triage output has somewhere well-formed to land. This is a smaller ask than the original CRM Requirements Discovery session — see Action Plan. Deal-flow side (Michael's future domain) still expected to migrate before investor-relationship data. Status: Not started.

### P-002 — Institutional relationships live in one person's head
- **Area:** People / Resources
- **Problem:** Investor relationships and deal history are almost entirely owned and remembered by Aaron personally — spread across his memory, text messages, and email, with no shared system. This creates single-person dependency and makes it impossible to delegate relationship management even as the team grows.
- **Current Thinking:** "It's messy, but I know where everything is" — the informal system works well enough for Aaron day-to-day, so there's been no forcing function to formalize it.
- **Reframe:** Untangling a large, unsystematized contact list gets exponentially harder the longer it's deferred — better to formalize while the volume is still manageable than after years of accumulated, un-institutionalized relationships (a failure pattern JC has seen repeatedly with executives).
- **Approach:** Build the shared CRM system in parallel with Aaron's existing informal habits (don't force an abrupt switch), then migrate once the new system is proven — "the switch flips once, and then the old system is never used again." Status: Not started.

### P-003 — No AI usage governance in place
- **Area:** Tools / People
- **Problem:** Michael and Aaron already use Claude in their work, but — per Barry and Martina's observation — without a clear understanding of the associated risks or best practices. As a result, more autonomous AI features (Claude's co-work, Notion's agent capabilities) are being deliberately left off, which also means the team isn't yet getting leverage from those tools.
- **Current Thinking:** AI usage guidelines feel like a "nice to have" that can wait until there's time to sit down and write something formal.
- **Reframe:** Written AI usage guidelines are cheap to produce, but valuable early — they create a standard the team can be held accountable to, and are far easier to put in place before scale than to retrofit afterward.
- **Approach:** Blue Tusk to adapt its existing AI-governance template (already built for "MakeHome") into a scaled-down version for a 2-person investing team, offered at no cost regardless of whether the broader engagement proceeds. **Updated 2026-08-18:** RFG has made this a hard gate — their one stated condition before widening tool access (specifically, turning on Claude Cowork) is reviewing and being comfortable with this document first. Status: In progress.

### P-004 — No inbound deal-flow intake or triage system
- **Area:** Processes / Systems
- **Problem:** The fund has no web form or structured intake for pitches/decks. Everything currently arrives ad hoc, and there's no systematic way to extract trend signal from the pitches that do come in, even though the team wants that visibility regardless of whether any given deal gets funded.
- **Current Thinking:** Deal flow feels secondary right now since there's no capital to deploy, so building intake infrastructure doesn't feel urgent.
- **Reframe:** Building the pipeline mechanics now — even while investing is paused — keeps the funnel "warm" and prevents having to restart market engagement from zero once Fund II capital exists; it also produces market-trend intelligence useful independent of investment decisions.
- **Approach:** Future workstream (after CRM foundation is in place): connect a website pitch-intake form to an automated flagging/categorization pipeline against the fund's investment criteria. Status: Not started (not yet scoped in detail).

### P-005 — Shared drive (SharePoint) not structured for AI use
- **Area:** Systems / Resources
- **Problem:** RFG's SharePoint was migrated to "as-is" from its prior state and was never restructured. As AI tools increasingly read shared drives directly, disorganized file structure creates "AI waste" — wasted effort, missed information, or the wrong information surfaced — and this problem compounds the longer it's deferred (JC has seen this be a brutal untangling process for organizations that wait until it's already a mess).
- **Current Thinking:** RFG already recognized this and deliberately chose not to deal with it during the SharePoint migration, planning instead to handle it later during Fund II data-room prep.
- **Reframe:** The Fund II data-room prep is exactly the forcing function that makes this the right moment — restructuring now, before the drive fills further and before more AI tooling reads it, avoids the painful retroactive untangling JC typically sees.
- **Approach:** JC to outline what a proper restructure involves for RFG and what oversight it requires from Blue Tusk, timed to align with Fund II data-room prep. Status: Opportunity identified, proposal pending from JC.

---

## 8. Action Plan

**Plan Overview:** Five problems are currently diagnosed, all clustered around the same root constraint: the fund's institutional knowledge (contacts, deals, and process) exists only informally — in Aaron's head, in an unconfigured Notion template, in ad hoc habits, and in an unrestructured shared drive — rather than in a shared, connected system. Aaron's top stated priority (maximize time on fundraising relationships) is served indirectly, by first building the infrastructure that lets relationship work be tracked, delegated, and eventually automated, rather than by any direct fundraising deliverable. **Updated 2026-08-18:** RFG deliberately narrowed the entry point — rather than a formal CRM requirements-discovery session, the first real build is AI-assisted triage of Aaron's inbox and calendar, which feeds the CRM as a byproduct. The sequencing logic is: governance first (a hard gate RFG imposed), inbox/calendar triage second (Aaron's actual bottleneck), deal-flow CRM third, sensitive personal-relationship data fourth, and forward-looking automation (pitch intake, shared-drive restructure, agentic workflows) last, once the underlying data structure and governance can support it.

### People
**In scope:** P-003
- **Workstream: AI Usage Governance Document**
  - Approach: Adapt Blue Tusk's existing AI-governance template (built for "MakeHome") for a 2-person investing team.
  - What it involves: Draft usage guidelines covering Claude and Notion AI features, risk areas, and accountability standards; review with Aaron, Michael, Martina, and Barry (for cybersecurity alignment).
  - Key Result: A written, agreed-upon AI usage policy the team can reference and be held to.
  - Timeline: Can start immediately, independent of the paid-engagement decision; days, not weeks.

### Systems / Processes
**In scope:** P-001, P-002, P-004, P-005
- **Workstream: Minimum CRM Structure** *(new, added 2026-08-18 — pushback on "feed the CRM cold")*
  - Approach: Before inbox/calendar triage starts, define the bare minimum CRM structure it needs to feed into — core fields (contact, org, deal stage, last-touch, next-touch) and the split between deal-flow and investor-relationship views. This is not the full CRM Requirements Discovery session; it's the smallest structural commitment that keeps triage output usable instead of adding mess faster.
  - What it involves: A short, focused conversation with Aaron (or Martina relaying) to lock the handful of fields and views that matter most — lighter than the original discovery session, but not skippable. JC's position: without this, AI-assisted inbox triage makes the CRM problem worse, not better, since it accelerates data entry into a structure that doesn't exist yet.
  - Key Result: A minimal, agreed field/view structure the inbox/calendar workstream can write into from day one.
  - Timeline: Immediately ahead of or alongside the inbox/calendar workstream — short, not a multi-week discovery process.

- **Workstream: AI-Assisted Inbox & Calendar Triage (Outlook)** *(actual first build, added 2026-08-18)*
  - Approach: Build a Claude-based triage assistant against Aaron's Microsoft 365/Outlook inbox and calendar — his confirmed real bottleneck — rather than starting with a formal CRM build. Gated on the AI governance document being reviewed and accepted (RFG's condition for turning on Cowork), and on Twintel clearing the necessary tenant permissions.
  - What it involves: JC to determine the cleanest technical path (Claude for Outlook add-in vs. alternatives) given Claude reads Gmail natively but not Exchange; coordinate with Martina/Twintel on tenant permissions; design the triage flow so it naturally populates CRM-relevant data as a byproduct.
  - Key Result: Aaron has a working inbox/calendar assistant reducing his admin load, and structured data starts flowing into the CRM without a separate cold-start data-entry effort.
  - Timeline: Next up after the governance document lands; blocked on Twintel permissions and JC's technical recommendation.

- **Workstream: CRM Requirements Discovery** *(deferred — superseded by the inbox/calendar workstream above as the actual entry point)*
  - Approach: Either a live 30-minute working session or an async flow (Aaron records himself talking through his CRM needs, ideally via Notion's meeting note-taker; Blue Tusk supplies a Claude prompt to extract structured follow-up questions from the recording).
  - What it involves: Define what data needs to live in the CRM, what the deal-flow vs. investor-relationship views need to contain, and how Aaron/Michael/Martina each need to interact with it.
  - Key Result: A documented set of CRM requirements and field definitions ready to build against.
  - Timeline: 1–2 weeks (blocked on Aaron's and JC's overlapping international travel; realistic restart is ~2 weeks after the second call).

- **Workstream: Master CRM Rebuild — Deal Flow First**
  - Approach: Single master Notion database with tagged views (deal/company vs. investor/contact), replacing the fragmented purchased template.
  - What it involves: Build the deal-flow/pipeline side first (new incoming deals, dead deals, prospects) since it's lower-sensitivity and will belong to Michael's future investment team; build in parallel with, not as a replacement for, Aaron's existing informal contact-tracking.
  - Key Result: A working, linked deal-flow database Michael can operate from, without requiring migration of Aaron's personal relationships yet.
  - Timeline: Concurrent with, but starting after, CRM Requirements Discovery; several weeks.

- **Workstream: Investor Relationship Migration**
  - Approach: Migrate Aaron's personal investor-relationship data (currently in his memory, texts, and email) into the master CRM once the deal-flow build and Aaron's comfort with the system are proven.
  - What it involves: A single deliberate "switch flip" migration rather than a gradual one, once the new system is validated.
  - Key Result: Investor relationship data lives in the fund's shared system, not solely in Aaron's head, and can eventually be assigned/delegated to other team members.
  - Timeline: After the deal-flow CRM workstream is stable — deliberately sequenced last among the CRM work.

- **Workstream: Notion CRM Skill (Contact Creation/Update)** *(new, added 2026-08-18)*
  - Approach: Build a Claude Skill against Notion's official Claude connector (already live, read/write) that encodes RFG's CRM schema once it's defined — so "add John from Acme, we talked today about their round" reliably produces a correctly-formatted, de-duplicated CRM entry instead of requiring manual data entry.
  - What it involves: (1) requires the CRM schema to exist first — depends on the Master CRM Rebuild workstream being far enough along to have a stable schema to build against; (2) the skill encodes duplicate-checking (search before create), field mapping, and next-touch/last-touch date logic — the same daily-dashboard concept originally floated in Meeting 2; (3) this is real write access to RFG's system of record, so it's a strong candidate for the *first* specific use case brought through the governance doc's Cowork-approval process once that's signed off.
  - Key Result: Aaron or Michael can create/update CRM contacts conversationally, with Claude handling correct formatting and de-duplication, closing the loop between the inbox/calendar triage workstream (which surfaces the contacts and touchpoints) and the CRM (which needs to store them consistently).
  - Timeline: After the Master CRM Rebuild has a stable schema, and after the governance doc is signed off (needed regardless, since this is a live-data write use case). Not urgent, but flagged now — Aaron should be aware this is coming and worth prioritizing once the schema work lands, since it's what actually removes the data-entry burden rather than just relocating it.

- **Workstream: Pitch Intake & Triage Pipeline**
  - Approach: Web form for inbound pitch decks, connected on the back end to automated criteria-flagging and categorization.
  - What it involves: Scope the website intake form, define investment criteria for auto-flagging, connect submissions into the master CRM.
  - Key Result: Inbound pitches are automatically captured, categorized, and flagged against criteria without manual sorting.
  - Timeline: After the master CRM foundation exists; not yet scoped in detail — later-stage workstream.

- **Workstream: Shared Drive (SharePoint) Restructure** *(new, added 2026-08-18)*
  - Approach: Structure RFG's SharePoint properly before it's read heavily by AI tooling, timed to align with Fund II data-room prep rather than done under pressure later.
  - What it involves: JC to define what "doing it right from the start" involves on RFG's side (folder/taxonomy structure, permissions, naming conventions) and what ongoing oversight this requires from Blue Tusk; present to Martina for the group.
  - Key Result: A documented restructure plan RFG can execute against ahead of or alongside Fund II data-room prep, avoiding a painful retroactive untangling.
  - Timeline: Proposal owed by JC; execution timing to align with Fund II data-room prep (not yet scheduled).

**Recommended Sequence:**
1. AI Usage Governance Document (People) — in progress; hard gate RFG imposed before widening tool access.
2. Minimum CRM Structure (Systems/Processes) — short, focused; needs to land before or alongside (3) so triage output has somewhere well-formed to go.
3. AI-Assisted Inbox & Calendar Triage (Systems/Processes) — depends on (1) and (2); Twintel's tenant-permission review is now confirmed complete (2026-08-18), so this no longer blocks.
4. Master CRM Rebuild — Deal Flow First (Systems/Processes) — the fuller buildout, informed by data surfaced in (3) on top of the structure set in (2).
5. Notion CRM Skill (Contact Creation/Update) (Systems/Processes) — depends on (4) producing a stable schema, and on (1) being signed off since this is a live-data write use case.
6. Investor Relationship Migration (Systems/Processes) — depends on (4) being stable and proven.
7. Pitch Intake & Triage Pipeline (Systems/Processes) — depends on (4), and ideally (6), being in place.
8. Shared Drive (SharePoint) Restructure (Systems/Processes) — can run in parallel with the above once JC's proposal is delivered; timing anchored to Fund II data-room prep rather than to the CRM sequence.

---

## 9. Engagement Metrics

- **Comprehension** — Ungraded — baseline. Aaron shows early understanding of the "why" (explicitly says he can't keep managing relationships from memory if he wants to scale to $50M), which is a positive early signal.
- **Adherence** — Ungraded — baseline.
- **Adoption** — Ungraded — baseline. Watch-point: co-work/agentic AI features are deliberately not yet enabled pending governance — adoption of deeper AI tooling should track behind the governance workstream, not ahead of it.
- **Velocity** — Ungraded — baseline. Watch-point: both Aaron and JC have back-to-back international travel immediately following the second call, creating a natural ~2-week pause before next steps can move.
- **Volume** — Ungraded — baseline. Currently low — one active workstream offered at no cost (AI governance), with CRM discovery pending internal sign-off.

---

## 10. Recommended Service Tier

Recommend starting in the **free engagement** tier already proposed to Aaron: no invoicing until value is demonstrably realized, governed by a free MSA. Given five active problems, several of which (CRM rebuild, inbox/calendar triage, investor-relationship migration, shared-drive restructure) involve real coordination load and sensitive data, plus two external technical/governance stakeholders to stay aligned with (Barry on cybersecurity, Twintel on tenant permissions), this will likely graduate to the **~$2,000/month tier** once the inbox/calendar and CRM work begin in earnest — consistent with the pricing already discussed with Aaron. Expect the free phase to run at least 1–2 months given the discovery, travel, and internal-alignment steps still pending.

---

*Sources: two meeting transcripts — (1) referral/scoping call between John-Carlos, Martina, and Barry; (2) introductory call with Aaron, Caroline, Martina, Barry, and John-Carlos — plus a 2026-08-18 email exchange between John-Carlos and Martina (with Aaron and Caroline consulted) following up on Meeting 2.*
