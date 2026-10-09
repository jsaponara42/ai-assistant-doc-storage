---
title: "Blue Tusk Shared Drive — Current Map + Proposed AI-First Taxonomy (Draft)"
date: 2026-10-07
tags: [project, strategy, tool, ai]
ai: claude
status: needs-attention
---

# Blue Tusk Shared Drive: Current Map + Proposed AI-First Taxonomy

## Summary
This maps the current folder structure of the Blue Tusk shared drive and proposes a new structure designed for AI agents to work in cheaply. Three goals drive it:
- **Token efficiency:** agents should reach the right folder in one or two calls, never by searching the whole drive.
- **Client isolation:** one client means one folder, contracts included.
- **A path to eventually moving the Obsidian vault into Drive.**

**This is a draft for JC to decide.** Nothing in the drive has been changed. The proposal applies Blue Tusk's own free-tier taxonomy principles ([[business/projects/internal/product/20260818_File_Taxonomy_Free_Tier_Principles]]) and the 2026-10-07 connector test findings ([[business/projects/internal/product/20261007_google-drive-taxonomy-test-results]]) to JC's own drive. It's dogfooding: whatever works here becomes the template for MOG and future taxonomy engagements.

## Decisions (JC, 2026-10-07)

### D-1. Group by client first, then project
Every client gets one folder, and each engagement is a project folder inside it. This replaces the vault's project-first grouping for Drive. Aligning the vault is a later follow-up, not changed now.

### D-2. Every client gets a short client code, and it's built into every project ID
- **Client code:** **3 capital letters, fixed length,** easy to remember, unique, and never reused, even after a client leaves. Registered in the root `INDEX`.
- **Project ID = `{CLIENT}-{YYMMDDNN}`**, e.g. `MOG-26092901`. *Recommendation: put the client code first* (JC said start or end; first is suggested):
  - The ID reads in the same order as the folder path (client, then project), so the ID **tells the agent which client folder to open.**
  - Searching `title contains 'MOG-'` finds every MOG project and file at once.
  - Lists sort by client in INDEX, Notion and the vault.
  - Inside a client folder every project shares the prefix, so they still sort by date.
  - The fixed-length prefix keeps IDs easy to read and parse.
- **Naming:**
  - Client folder: `{CLIENT}_{client-slug}`, e.g. `MOG_madrid-operations-group/`
  - Project folder: `{CLIENT}-{YYMMDDNN}_{project-slug}`, e.g. `MOG-26092901_ai-first-retainer/`
  - Files: `{YYYYMMDD}_{CLIENT}-{YYMMDDNN}_{description}`, or `{YYYYMMDD}_{CLIENT}_{description}` for client-level files such as the brief or contracts.
- **Internal Blue Tusk work** uses its own code, proposed `BTK`, e.g. `BTK-26100701_drive-restructure`.

**Proposed client codes (for JC to confirm or change):**

| Client | Proposed code | Existing projects |
|---|---|---|
| Madrid Operations Group | MOG | MOG-26092901 (AI-first retainer) |
| LendForGood | LFG | LFG-26091801 (Xero automation) |
| Ruthless For Good | RFG | RFG-26073101 (discovery) |
| Maycomb Capital | MAY | MAY-26061601 (AI roadmap) |
| Capital Financing | CAP | CAP-26061201 (AI & automation advisory) |
| NeighborWorks Capital | NWC | NWC-26061701 (AI roadmap) |
| CauseCrazy (Rocky Fischer) | CCZ | CCZ-25121701 (first project) |
| Ellison Helmsman (Josh Henderson) | EHM | `[TO CONFIRM project date]` |
| RightWayRealty Group (Conrad Martin) | RWR | `[TO CONFIRM]` |
| SyncScript | SYN | `[TO CONFIRM]` (proposal, 2024–2025) |
| Pine Run Construction | PRC | `[TO CONFIRM]` (currently under "AI Advisory - All") |
| Blue Tusk (internal) | BTK | e.g. BTK-26100701 (this restructure) |

*Note:* MOG uses "MC" internally for Maycomb. Blue Tusk's registry is Blue Tusk's own, but agreeing on one code per entity across Blue Tusk and MOG (free-tier principle #2) is worth considering, since both work with the same clients.

### D-3. AI isolation rule: across projects yes, across clients never
- **Allowed:** an agent working on a client can read **every project inside that client's folder.** Earlier engagements are exactly the context that should shape new work for the same client.
- **Not allowed:** an agent working on a client must **never read, search or write in another client's folder.** This keeps information from one client out of another client's work and keeps confidentiality intact.
- **How this is enforced:**
  - The client code in the project ID tells the agent its scope: `MOG-…` means `01_Clients/MOG_…/` only.
  - Agents work from folder IDs listed in INDEX, never from full-text search across the drive. Search returns every client's files, as shown in the 2026-10-07 test.
  - Each client gets its own Claude Project, loaded with CONVENTIONS plus that client's brief and folder.
- **Shared internal material** (`04_Offers/`, `05_Knowledge/`, templates) can be used for any client's task, **as long as it holds no client-specific information.** Anything learned from one client goes into shared folders only after JC has stripped out the client details and turned it into general guidance. Agents never copy client material into shared folders on their own.

## Context
- JC wants to restructure his Google Drive to make the most of Claude's Google connectors, and to eventually move the vault from local Obsidian to a cloud service like Drive. **Token efficiency is the main thing to figure out.**
- Mapped 2026-10-07 by listing folders through the Drive connector. Folders only, no file contents.
- **Coverage caveat:** the folder search pages unpredictably, sometimes 5 results per page and sometimes ~100. It also mixes in other drives. The map below covers everything returned for the Blue Tusk shared drive, but folders that haven't been opened in a long time could be missing. JC should check it against the Drive UI before acting on it.
- **Other drives also showed up:**
  - A second shared drive (root `0AJ44i8f…`) containing `01_Working Desk - Jan`, `00_Active Project Cards`, `03_Files to Process`, `04_References`, `.claude`, contact folders like `PER-…`, Rudin Law and Petro Mechanical. *(Inferred: a client's drive JC has access to; looks Capital Financing-related.)* Left out of the map.
  - **JC's My Drive** (`jcsaponara@bluetuskbio.com`) holds Blue Tusk material outside the shared drive: `CAUSE Lead Magnets` (01 - Leads, 02 - ICP + AdWords Docs, Testing), `SOP`, `Blue Tusk Stuff`.

---

## Content

### 1. Current map (Blue Tusk shared drive, folders only)

```
Blue Tusk (shared drive root)
├── Admin/
│   ├── Daily Accountability/
│   └── HR/
├── Business Development/
│   ├── AGP/
│   │   ├── Delivery/
│   │   ├── Foundations/
│   │   ├── Outbound Systems/   (Audits/, Media/, Notes/, ARCHIVE/)
│   │   └── Sales/
│   ├── Company Strategy/
│   │   └── Product Strategy/
│   │       └── Blue Tusk AI Audit/
│   │           └── Marketing It/
│   ├── GhostOps/
│   ├── Relationships/
│   │   └── Advisor Outreach/
│   └── Vendors/
├── Client Projects/
│   ├── AI Advisory - All/
│   │   ├── 1 - Industry Templates/
│   │   └── Pine Run Construction/
│   ├── Capital Financing/
│   │   └── 26061201 - Capital Financing - AI and Automation Advisory/
│   ├── CauseCrazy - Rocky Fischer/
│   │   ├── 00_ClientResources/
│   │   │   └── XX_Logins/                        ⚠ credentials in Drive
│   │   └── 01 - First Project - 20251217/
│   │       ├── AI and Automation Audit/
│   │       ├── Background Docs/  (CAUSE Lead Magnet Prompts/)
│   │       └── Development/      (CAUSE Lead Magnet/Prompts/)
│   ├── Josh Henderson - Ellison Helmsman/
│   │   ├── DELIVERED - Automation Documentation/
│   │   └── Make Automation Sheets/
│   ├── LendForGood/
│   │   └── 26091801_Xero-automation/
│   ├── Madrid Operations Group/
│   │   └── 26092901-AI Workflow Rebuild/
│   ├── Maycomb Capital/
│   │   └── 26061601 - AI Roadmap (Free)/
│   ├── NeighborWorks Capital/
│   │   └── 26061701 - AI Roadmap (Free)/
│   ├── RightWayRealty Group - Conrad Martin/
│   ├── Ruthless For Good/
│   │   └── 26073101 - Discovery (Free)/
│   └── SyncScript (Proposal)/
│       ├── 2024/
│       └── 202502 - Excel Transcription/
├── Finance/
│   ├── Archive/
│   │   ├── Monthly Expense Trackers/  (ARCHIVE_Individual Month/)
│   │   └── Monthly Revenue Trackers/
│   ├── Expense Reciepts/
│   │   ├── 2024 Reciepts/   (202402 … 202412)
│   │   ├── 2025 Reciepts/   (202501 … 202512)
│   │   └── 202601, 202602, 202603, 202604     ← 2026 not grouped by year
│   ├── Legal Finance/       (Capital Contributions/, Loans/)
│   ├── Monthly Bookkeeping/ (2024 Bookkeeping/, 2025 Bookeeping/)
│   └── Monthly Cash Flow Projections/ (Archive/)
├── Legal/
│   ├── Contracts/
│   │   ├── Examples/
│   │   ├── Signed/
│   │   │   └── MSA/  (LendForGood/, Maycomb Capital/, Ruthless For Good/)
│   │   └── Unsigned/
│   ├── HIPAA/
│   ├── LLC/  (Compliance/, NYS Publication Requirement/)
│   ├── NDA/  (Signed/)
│   └── Tax/
├── Marketing/
│   ├── Blog/            (Content Factory Outputs/, Resources/)
│   ├── Images/          (Headshots/, Logo/, Social Media/)
│   ├── Marketing Copy/
│   │   ├── Blog Posts/  (Blog Images Files/)
│   │   ├── Cold Email Campaigns/  (Active/, Past/)
│   │   ├── Instagram Posts/
│   │   ├── LinkedIn Posts/
│   │   └── Pillar Content Method/ (1 - Core Pillar Content … 6 - Instagram Reels)
│   ├── Marketing Strategy/
│   │   └── Market Research/ (Competitor Research/)
│   └── Sales Collateral/
│       ├── Data Sheets/, Infographics/, In Progress/, One-Pagers/, VSL/
│       ├── Lead Magnets/ (xx_ARCHIVE/: General/, Construction/, PI Law/)
│       └── Whitepapers/  (Whitepaper Planning/)
├── Product/
│   ├── AI and Automation Audit Partnership/
│   │   └── Support Materials/ (Delivery/, Technical Info/)
│   └── New Product Development/
│       └── AI and Automation Advisor/
├── Project Resources/          (no subfolders found)
├── Sales/
│   ├── Cold Resources/
│   │   └── Cold Email/
│   │       └── Lead List/
│   │           ├── Verified/   (PI Law/2025/, Business Valuators/, Misc/, XX_Raw/)
│   │           └── Un-Verified/
│   ├── Proposals + SOW/
│   │   ├── ROI Calculations/
│   │   └── SOW/  (Sold/, Lost/)
│   ├── Sales Strategy/
│   └── Scripts/  (General/, Learning and Resources/, PI Firm - Free Audit Offer/)
└── Taxonomy Test/              (2026-10-07 connector test; disposable)
```

### 2. What the map shows

**Things that cost agents tokens (or cause wrong answers):**
1. **Client information is split across two trees.**
   - Signed MSAs live in `Legal/Contracts/Signed/MSA/{client}`.
   - Project work lives in `Client Projects/{client}`.
   - SOWs live in `Sales/Proposals + SOW/SOW/Sold/`.
   - An agent asked about "LendForGood" has to search three places, or search the whole drive, which also returns other clients' files.
2. **The same work is spread across sales, BD and marketing.**
   - Cold email appears under `Marketing/Marketing Copy/Cold Email Campaigns` and also `Sales/Cold Resources/Cold Email`.
   - Strategy is split three ways: `Business Development/Company Strategy`, `Sales/Sales Strategy`, `Marketing/Marketing Strategy`.
   - Product strategy sits under BD while `Product/` is a separate top-level folder.
   - An agent can't tell which copy is current.
3. **Inconsistent naming makes it hard to guess where things are.**
   - Project codes use three formats: `26061601 - AI Roadmap (Free)`, `26091801_Xero-automation`, `26092901-AI Workflow Rebuild`.
   - Client folders are a mix of company names and "Person - Company" (`CauseCrazy - Rocky Fischer`, `Josh Henderson - Ellison Helmsman`).
   - Archive folders appear as `xx_ARCHIVE`, `ARCHIVE`, `Archive` and `ARCHIVE_Individual Month`.
   - Typos: `Reciepts`, `Bookeeping`.
4. **Archives sit inside working folders,** so stale material shows up in listings and searches.
5. **Finance years are inconsistent.** 2024 and 2025 receipts are grouped by year, while 2026 months sit loose.
6. **Some folders are unclear:** `AGP`, `GhostOps`, `Project Resources` (empty?), `AI Advisory - All` (a template library mixed in with a client).
7. **Blue Tusk material lives outside the shared drive** in JC's My Drive (CAUSE lead magnets, SOP).

**Security flag:** `Client Projects/CauseCrazy - Rocky Fischer/00_ClientResources/XX_Logins/` suggests credentials are stored in Drive. Anything in Drive can be read by any connected AI agent. Logins belong in a password manager, not Drive, regardless of the restructure.

**What already works well:**
- The vault-style project codes (`YYMMDDNN`) are already used in the newer client folders.
- The newer client folders already follow a "one folder per engagement" pattern.

### 3. Design principles for JC's drive (token efficiency first)

| # | Principle | Why it saves tokens or prevents errors |
|---|---|---|
| 1 | **One client = one folder,** holding contracts, proposals, project work and AI notes. Agents may work across that client's projects, never across clients (D-3). | An agent scoped to that folder finds everything about the client with one listing. No whole-drive search, no cross-client leaks. |
| 2 | **Shallow tree:** at most ~3 levels to any working file | Each level is a listing call. Deep nesting multiplies calls, and listings page unpredictably. |
| 3 | **Predictable names, one convention everywhere** (free-tier principles #2–3) | Agents can build the path from the convention instead of searching. |
| 4 | **A folder-ID index at the root** (registry: code → Drive folder ID) | The single biggest saving. An agent reads one small index and jumps straight to the right folder by ID, with zero searching. |
| 5 | **Same codes as the vault** (`YYMMDDNN` projects; client slugs) | One identifier across Drive, the vault and Notion (free-tier principle #2). That makes a later vault-to-Drive move a mapping rather than a redesign. |
| 6 | **One root-level `99_Archive/`** that mirrors the structure | Keeps stale files out of working listings and searches (free-tier principle #4). |
| 7 | **Non-text assets in clearly named asset folders** (images, video, PDFs of receipts) | Agents can skip them, so listings stay small and relevant. |
| 8 | **AI working space per client (`_ai/`) and at the root** | Agent notes and handoffs live in a known place. **Storage format is unresolved (D9);** see the test log. |
| 9 | **No secrets in Drive** | Any connected agent can read anything in Drive. |

### 4. Proposed structure (draft, for JC to react to)

```
Blue Tusk (shared drive)
├── CONVENTIONS                         ← how to navigate; read first
├── INDEX                               ← registry: client code → client name → client folder ID; project ID → project folder ID → vault path → status
├── _ai/                                ← JC's own agent notes and handoffs (format per D9)
│
├── 00_Company/                         ← evergreen company infrastructure
│   ├── Admin/          (HR, accountability)
│   ├── Legal/          (LLC & compliance, tax, HIPAA, contract TEMPLATES & examples only)
│   └── Finance/
│       ├── Bookkeeping/{YYYY}/
│       ├── Receipts/{YYYY}/{YYYYMM}/
│       └── Planning/   (cash flow, revenue/expense trackers, capital contributions, loans)
│
├── 01_Clients/
│   └── {CLIENT}_{client-slug}/         e.g. MOG_madrid-operations-group/
│       ├── {date}_{CLIENT}_Client-Brief
│       ├── _ai/                        ← handoff, agent notes, rough drafts (format per D9)
│       ├── 00_Contracts/               ← signed MSA, NDA, every SOW for this client
│       └── {CLIENT}-{YYMMDDNN}_{project-slug}/  e.g. MOG-26092901_ai-first-retainer/
│           ├── meetings/ · decisions/ · drafts/ · delivered/   (only as needed)
│
├── 02_Pipeline/                        ← sales + BD merged: anything not yet a client
│   ├── Prospects/{prospect-slug}/      (moves to 01_Clients/ when signed)
│   ├── Partners/                       (referral partners, vendors, advisors: AGP? GhostOps?)
│   ├── Outreach/                       (scripts, cold email sequences, lead lists)
│   └── Proposals-Templates/            (proposal, SOW, ROI calculators)
│
├── 03_Marketing/
│   ├── Brand-Assets/                   (logo, headshots, images: agents skip)
│   ├── Content/{channel}/              (LinkedIn, blog, Instagram, video, pillar content)
│   └── Lead-Magnets/                   (CAUSE lead magnets moved in from My Drive)
│
├── 04_Offers/                          ← what Blue Tusk sells and how it's delivered
│   ├── {offer-slug}/                   (AI Roadmap, Taxonomy, AI-First Rebuild, Audit Partnership…)
│   │   └── definition, delivery playbook, templates (Industry Templates move here)
│   └── Strategy/                       (company, product, sales, marketing strategy, in ONE place)
│
├── 05_Knowledge/                       ← internal SOPs, research, market/competitor research
│
└── 99_Archive/                         ← mirrors the tree above; nothing active lives here
```

**How the proposal maps to the vault (for an eventual move):**

| Vault | Proposed Drive |
|---|---|
| `business/projects/client-projects/{YYMMDDNN_slug}/` | `01_Clients/{CLIENT}_{client-slug}/{CLIENT}-{YYMMDDNN}_{project-slug}/` (**decided: client first, D-1.** Aligning the vault is a later follow-up.) |
| `business/SOPs/`, `business/research/` | `05_Knowledge/` |
| `business/projects/internal/` | `04_Offers/` + `05_Knowledge/` |
| `business/marketing/` | `03_Marketing/` |
| `business/sales/` | `02_Pipeline/` |
| `tasks/`, `TASK-LOG.md`, `CONVENTIONS.md` | Root `INDEX` / `CONVENTIONS` + `_ai/` (format per D9) |
| `xx_context-handoff.md` per project | `_ai/` per client or project |

### 5. The constraint that matters for the move
**Agents can't move files in the shared drive** (tested 2026-10-07: permission error on moves, even with Manager access; rename and trash work). So the migration **can't be done by Claude through the current connector**. The options:
- **JC moves files by hand in the Drive UI** (drag and drop keeps IDs, links and sharing). With this many folders, that's a few focused hours.
- **A Google Apps Script** run by JC that does the moves from a mapping table Claude writes. It's fast and repeatable, but needs a careful dry run first.
- **Claude creates the new skeleton** (folders plus CONVENTIONS and INDEX, which works) **and JC drags the content in.**

Per the offering-stack note's open question on migration, this is also a real-world test of incremental vs big-bang migration, and should be logged as such.

### 6. Token-efficiency notes specific to the vault move
- Moving the vault's markdown into Drive runs straight into the **unresolved D9 problem:** real `.md` files can't be edited in place through the current connectors. Moving JC's vault to Drive before D9 is resolved would make every vault edit costlier, or force the plain-Google-Doc workaround.
- **Until D9 is resolved:** keep the vault local (the `vault` MCP server's cheap find-and-replace edits are the best case today). Put finished, human-facing outputs in Drive, and use INDEX to link vault paths to Drive folder IDs.
- **Option E from the test log (a custom Drive-markdown MCP server)** would bring the vault server's cheap editing to Drive. It's the most direct route to a cloud vault, and the same build could serve MOG and future clients.

---

## Next steps
- [ ] **JC:** check the map in the Drive UI and add any folders the listing missed.
- [ ] **JC:** explain `AGP`, `GhostOps`, `Project Resources`, and what the second shared drive is.
- [x] **JC:** decide whether client folders group by client first or project first. **Decided 2026-10-07: client first (D-1), client codes in project IDs (D-2), AI isolation rule (D-3).**
- [x] **JC:** confirm the proposed client codes and client-code-first IDs. **Confirmed 2026-10-09.** `[TO CONFIRM]` project dates for EHM, RWR, SYN, PRC still open.
- [ ] **JC:** decide the rest of the top-level structure (Section 4).
- [ ] Write the isolation rule (D-3) into the Drive `CONVENTIONS` file when it's built, and into the agent rules for MOG.
- [ ] Later: decide whether to restructure the vault to client-first to match Drive.
- [ ] **JC:** move `XX_Logins` contents into a password manager and delete the folder.
- [x] Decide the migration method (Section 5). **Skeleton approach; built 2026-10-09:** [[20261009_blue-tusk-drive-skeleton-build]]. JC drags content in.
- [ ] Revisit D9 before any vault-to-Drive move.


---

## Update 2026-10-08: decisions that change this proposal

Full design: [[business/projects/internal/product/20261008_ai-native-operating-architecture]]. Decision history: [[business/projects/internal/product/20261008_ai-native-architecture-decision-log]].

- **Drive holds finals and files only.** Drafts, client and project context, CRM, tasks, meeting notes and registers live in Notion. The `_ai/` folders in Section 4 are **dropped**; agent notes and handoffs live in Notion.
- **Project folders get standard subfolders:** `client-sent/` (originals from clients, registered in Notion Documents) and `delivered/` (copies of what went to the client). **Client folders get `00_Contracts/`** for signed MSAs, NDAs and SOWs (registered in Notion Contracts).
- **Files are named by audience:**
  - **Internal:** `YYYYMMDD_{CLIENT}-{YYMMDDNN}_description`.
  - **Client-facing finals:** clean titles with no date, ID or "draft", e.g. `AI-First Rebuild - Build Plan`.
- **INDEX** adds a Notion link per client and project.
- **Backups never live where the Claude-connected account can see them.** That rules out a backup folder in this shared drive unless that account is excluded.
- **Invoices:** Stripe is the source of truth for Blue Tusk; Notion keeps the register. No invoice folder in Drive.
- **Blank templates** go in `04_Offers/` or `05_Knowledge/`; the instructions for them live in Notion Knowledge.
- **Still open:** confirming the client codes and the rest of the top-level structure, and the `XX_Logins` folder clean-up (security).
