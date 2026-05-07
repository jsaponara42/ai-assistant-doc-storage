---
title: "GhostOps CMS — Product Requirements Document"
date: 2026-05-07
tags: [project, strategy, tool]
ai: claude
status: needs-attention
---

## Summary

Formal PRD for the GhostOps Case Management System (CMS) — a legal case management platform built for personal injury law firms, designed around a unified note-based data model, accessible via web UI, CLI, and REST API, and built on AWS with Python. The system is architected from day one for compliance, reliability, and AI-agent accessibility.

## Context

Derived from the initial product voice note ([[2026-05-07-ghostops-cms-braindump]]). This document is the authoritative product requirements reference for all GhostOps CMS development. It covers product vision, target user, feature requirements, data model, technical architecture, compliance requirements, and phased delivery plan.

---

## Content

---

# GhostOps CMS — Product Requirements Document

**Version:** 0.1 (Initial)
**Date:** 2026-05-07
**Status:** Draft — Needs Review
**Author:** JC (via AI-assisted structuring)

---

## 1. Product Vision

GhostOps CMS is a modern, API-first legal case management system built for personal injury law firms. It replaces bloated legacy platforms (FileVine, Clio, LeadDocket, SmartAdvocate) with a lean, intuitive, and extensible system that law firms can actually use — and that AI agents can operate programmatically.

The core design principle is simplicity through unification: **everything is a note.** Tasks, calendar events, calls, documents, and communications are all variants of the same underlying object, attached to a case. This keeps the data model flat, the UI consistent, and the API predictable.

The system is built to grow. The MVP establishes the foundation — case records, note management, document storage, and the three access layers (UI, CLI, API). Everything added after MVP plugs into that foundation without rebuilding it.

---

## 2. Target Users

### Primary: Personal Injury Law Firm Staff

| Role | Primary Use |
|---|---|
| Attorney | Review cases, sign off on tasks, draft/review documents |
| Paralegal | Day-to-day case management, note entry, task tracking |
| Case Manager | Status tracking, client communication logging, milestone management |
| Intake Coordinator | New case creation, initial data entry, lead tracking |
| Firm Administrator | User management, reporting, firm-wide configuration |

### Secondary (Post-MVP)

- Other plaintiff-side practice areas (workers' comp, mass tort, employment)
- Defense-side firms (future expansion, requires configuration changes)
- AI agents operating on behalf of any of the above roles

---

## 3. Problem Statement

Personal injury law firms manage high-volume, time-sensitive caseloads across many simultaneous matters. Current tools fail them in predictable ways:

- **Legacy UX** — most incumbent platforms were built 10–15 years ago and show it
- **Fragmented data** — tasks, notes, calls, and calendar items live in different objects, making it hard to get a unified view of a case
- **Poor API design** — integrations are brittle, expensive, or unavailable
- **No AI readiness** — no system today is built to be operated by an AI agent
- **Lock-in** — data export and migration from incumbents is painful by design

GhostOps CMS solves all five.

---

## 4. Core Design Principles

1. **Everything is a note.** All case activity — tasks, calls, calendar entries, internal memos — is a note with a type. One object. One table. One API endpoint family.
2. **API-first.** Every action available in the UI is available via API. The UI is a client of the API, not a special case.
3. **CLI parity.** Every core operation available via API is available via CLI. AI agents use the CLI and/or API interchangeably.
4. **Modular metadata.** Case fields are not hardcoded. The PI template ships out of the box; new practice area templates can be added without schema migrations.
5. **Compliance by default.** Data handling, encryption, audit logging, and access controls are not bolted on later — they are designed in from the start.
6. **Drill down, not scroll.** The UI is organized around progressive disclosure: firm → cases → case → notes/documents/timeline. Each layer is fast to reach and easy to navigate.

---

## 5. Feature Requirements

### 5.1 Case Management

#### 5.1.1 Case Record

Every case is a first-class object with a unique ID. A case record contains:

**Core fields (all practice areas):**

| Field | Type | Notes |
|---|---|---|
| `case_id` | UUID | System-generated |
| `case_name` | String | e.g., "Smith v. Johnson" |
| `case_number` | String | Firm-assigned or court-assigned |
| `practice_area` | Enum | PI, workers comp, mass tort, etc. |
| `status` | Enum | See §5.1.2 |
| `phase` | FK → Phase | See §5.1.2 |
| `date_opened` | Date | |
| `date_closed` | Date | Nullable |
| `assigned_attorney` | FK → User | |
| `assigned_paralegal` | FK → User | Nullable |
| `assigned_case_manager` | FK → User | Nullable |
| `created_at` | Timestamp | |
| `updated_at` | Timestamp | |

**PI-specific metadata fields (template):**

| Field | Type | Notes |
|---|---|---|
| `incident_date` | Date | Date of the injury/accident |
| `incident_type` | Enum | Auto accident, slip & fall, med mal, etc. |
| `incident_description` | Text | Free text |
| `jurisdiction` | String | State/county/court |
| `statute_of_limitations` | Date | SOL deadline — critical field |
| `client_id` | FK → Contact | |
| `defendant_ids` | FK[] → Contact | One or more |
| `insurance_carrier` | String | Primary carrier name |
| `policy_number` | String | |
| `claim_number` | String | |
| `adjuster_name` | String | |
| `adjuster_phone` | String | |
| `adjuster_email` | String | |
| `demand_amount` | Decimal | |
| `settlement_amount` | Decimal | Nullable |
| `lien_holders` | JSON | Array of lien objects |
| `treating_providers` | FK[] → Contact | Medical providers |
| `medical_records_status` | Enum | Not requested / Requested / Received / Complete |
| `police_report_number` | String | |
| `police_report_received` | Boolean | |
| `liability_assessment` | Enum | Strong / Moderate / Weak / Unknown |
| `referral_source` | String | |
| `co_counsel` | FK → User / String | Internal or external |

**Custom fields:** Firms can define additional fields per practice area. Custom fields are typed (string, number, date, boolean, enum, multi-select) and can be marked required or optional.

#### 5.1.2 Case Status & Phase Model

Cases move through a defined lifecycle. Status and phase are separate concepts.

**Status** (is the case active?):

- `active` — case is open and being worked
- `on_hold` — case is paused (reason required)
- `closed_settled` — resolved via settlement
- `closed_verdict` — resolved via trial verdict
- `closed_dismissed` — case dismissed
- `closed_declined` — firm declined to take the case
- `archived` — closed and archived

**Phase** (where is the case in its lifecycle?):

Phases are stored as rows in a `phases` table with an explicit `sort_order` integer that controls display sequence in the UI picker. Phase names are clean and human-readable — no numeric prefixes needed (those exist in systems like FileVine only to work around the lack of configurable ordering). The UI groups phases by category for easier navigation.

The default PI phase set, in display order:

**Intake & Early Case**

| Phase Name | Key | Description |
|---|---|---|
| New File | `new_file` | Case just created; not yet assigned or actively worked |
| File Set-Up | `file_setup` | Retainer signed; contacts, insurance, and incident info being entered |
| Investigation Only | `investigation_only` | Liability investigation underway; no full sign-up yet |
| DV/PD Only | `dv_pd_only` | Diminished value or property damage only; no bodily injury claim |

**Treatment**

| Phase Name | Key | Description |
|---|---|---|
| Treatment < 90 | `treatment_lt_90` | Client in active treatment; fewer than 90 days since incident |
| Treatment > 90 | `treatment_gt_90` | Client in active treatment; 90–180 days since incident |
| Treatment > 180 | `treatment_gt_180` | Client in active treatment; 180–360 days since incident |
| Treatment > 360 | `treatment_gt_360` | Client in active treatment; 360–540 days since incident |
| Treatment > 540 | `treatment_gt_540` | Client in active treatment; over 540 days since incident |
| Released Pending Records | `released_pending_records` | Client discharged from treatment; awaiting medical records |
| Ready for Demand | `ready_for_demand` | All records received; case ready to build demand package |

**Demand — Liability (Third-Party)**

| Phase Name | Key | Description |
|---|---|---|
| Demand Approval (Liab) | `demand_approval_liab` | Demand package complete; pending attorney review and approval before sending |
| Demand in Prep (Liab) | `demand_prep_liab` | Demand letter being drafted against liability carrier |
| Demand Sent (Liab) | `demand_sent_liab` | Demand sent to liability carrier; awaiting response |
| Negotiations (Liab) | `negotiations_liab` | Active settlement negotiations with liability carrier |

**Demand — UM/UIM (Uninsured/Underinsured Motorist)**

| Phase Name | Key | Description |
|---|---|---|
| Demand Approval (UM/UIM) | `demand_approval_umuim` | Demand package complete; pending attorney review and approval before sending |
| Demand in Prep (UM/UIM) | `demand_prep_umuim` | Demand letter being drafted against UM/UIM carrier |
| Demand Sent (UM/UIM) | `demand_sent_umuim` | Demand sent to UM/UIM carrier; awaiting response |
| Negotiations (UM/UIM) | `negotiations_umuim` | Active settlement negotiations with UM/UIM carrier |

**Settlement & Resolution**

| Phase Name | Key | Description |
|---|---|---|
| Settlement | `settlement` | Settlement agreement reached; finalizing terms |
| Settlement Statement Prep | `settlement_statement_prep` | Preparing settlement statement and disbursement breakdown |
| Lien Resolution | `lien_resolution` | Negotiating and resolving outstanding liens before disbursement |
| Disbursement Ready | `disbursement_ready` | All liens resolved; cleared to disburse funds |
| Disbursement | `disbursement` | Funds actively being disbursed to client and lien holders |

**Litigation**

| Phase Name | Key | Description |
|---|---|---|
| Lawsuit Prep | `lawsuit_prep` | Preparing complaint and litigation documents |
| Lawsuit Filed | `lawsuit_filed` | Complaint filed with the court |
| Lawsuit Pending Service | `lawsuit_pending_service` | Complaint filed; awaiting service of process on defendant(s) |
| Defendant Answer Due | `defendant_answer_due` | Defendant served; answer deadline pending |
| Written Discovery | `written_discovery` | Written discovery underway (interrogatories, RFPs, RFAs) |
| Depositions | `depositions` | Deposition phase active |
| Mediation | `mediation` | Case referred to mediation |
| Pre-Trial Motions | `pre_trial_motions` | Motions in limine, summary judgment, and other pre-trial motions |
| Trial | `trial` | Active trial |
| Appeal | `appeal` | Post-verdict appeal filed |

**Referred Out**

| Phase Name | Key | Description |
|---|---|---|
| Referred Out Pre-Lit | `referred_out_pre_lit` | Case referred to another firm before litigation was filed |
| Referred Out | `referred_out` | Case referred to another firm (general) |
| Referred Out Lit | `referred_out_lit` | Case referred out while in active litigation |
| Referred Out Settlement | `referred_out_settlement` | Case referred out during settlement phase |
| Referred Out Mass Torts | `referred_out_mass_torts` | Case referred to a mass tort firm |

**Closed / Terminal**

| Phase Name | Key | Description |
|---|---|---|
| Withdrawal by Firm | `withdrawal_by_firm` | Firm withdrew from representation |
| Terminated by Client | `terminated_by_client` | Client terminated the firm's representation |
| Always Open | `always_open` | Administrative or evergreen matter; no expected close date |
| Archived | `archived` | Case fully closed and archived |

**MVP note:** The phase list above ships as the fixed default PI template and is not user-editable in MVP. Custom phase management — adding, renaming, reordering, or deactivating phases — is a post-MVP feature. Because display order is stored as an explicit `sort_order` field on each phase record (not derived from the name or key), enabling custom ordering post-MVP requires no data migration or schema change.

Phase transitions are logged automatically as a `system_event` note on the case timeline. The UI phase picker displays phases in `sort_order` sequence, visually grouped by category.

#### 5.1.3 Case List & Sorting

The case list view must support:

- Filter by: status, phase, assigned staff, practice area, date opened range, SOL window
- Sort by: date opened, SOL date, last activity, case name, assigned attorney
- Search by: case name, client name, case number, claim number
- Saved filter presets per user
- Bulk actions: reassign, change status, export

#### 5.1.4 SOL Tracking

The statute of limitations date is a critical field. The system must:

- Surface SOL dates prominently in the case list (color-coded: green > 90 days, yellow 30–90, red < 30)
- Send configurable alerts (in-app + email) at 90, 60, 30, 14, 7 days before SOL
- Log all SOL date changes as an auditable system event note

---

### 5.2 The Note System

This is the heart of the product.

#### 5.2.1 What is a Note?

A note is any discrete unit of activity or information attached to a case. All note types share a common base schema, extended by type-specific fields.

**Base note schema:**

| Field | Type | Notes |
|---|---|---|
| `note_id` | UUID | System-generated |
| `case_id` | FK → Case | Required |
| `note_type` | Enum | See §5.2.2 |
| `title` | String | Short description |
| `body` | Text | Main content (markdown supported) |
| `created_by` | FK → User | |
| `created_at` | Timestamp | |
| `updated_at` | Timestamp | |
| `due_date` | Date | Nullable — populated for tasks and calendar items |
| `assigned_to` | FK → User | Nullable — populated for tasks |
| `completed` | Boolean | Default false |
| `completed_at` | Timestamp | Nullable |
| `completed_by` | FK → User | Nullable |
| `visibility` | Enum | `internal` / `shared` (future: client portal) |
| `pinned` | Boolean | Pin to top of case timeline |
| `tags` | String[] | Free tags for filtering |
| `linked_notes` | UUID[] | References to related notes |
| `attachments` | FK[] → Document | Documents attached to this note |
| `system_generated` | Boolean | True if created by automation/AI |

#### 5.2.2 Note Types

| Type | Description | Key Additional Fields |
|---|---|---|
| `general` | Freeform internal note | — |
| `task` | An action item assigned to someone | `assigned_to`, `due_date`, `priority` |
| `calendar_event` | A scheduled event | `start_time`, `end_time`, `location`, `attendees` |
| `call_log` | Record of a phone call | `direction` (in/out), `duration`, `contact_id`, `outcome` |
| `email_log` | Record of an email exchange | `direction`, `contact_id`, `subject`, `thread_id` |
| `medical_record_request` | Tracking a records request | `provider_id`, `requested_date`, `received_date`, `records_period` |
| `demand_log` | Demand letter sent | `demand_amount`, `sent_date`, `carrier`, `adjuster` |
| `offer_log` | Settlement offer received/made | `offer_amount`, `direction`, `expiration_date` |
| `court_event` | Hearing, deposition, trial date | `court`, `judge`, `event_subtype`, `start_time` |
| `document_upload` | Document added to case | Auto-generated when document uploaded |
| `status_change` | Case status or phase changed | Auto-generated by system |
| `system_event` | Any other system-generated activity | `event_key` |
| `ai_draft` | AI-generated document draft | `model`, `prompt_summary`, `approved_by` |

#### 5.2.3 Note Views

Users can view notes in multiple modes per case:

- **Timeline** — all notes chronologically (default)
- **Tasks** — filter to tasks only, grouped by status (open / overdue / completed)
- **Calendar** — calendar events and court dates in calendar view
- **Activity feed** — all notes, newest first, with type icons
- **Filtered** — any combination of note types, date range, assigned user, tag

#### 5.2.4 Task Management

Tasks are notes with `note_type: task`. Required fields beyond base:

- `priority` — `low` / `normal` / `high` / `urgent`
- `assigned_to` — FK to user (required for tasks)
- `due_date` — required for tasks

My Tasks view: a global view (not per-case) showing all tasks assigned to the logged-in user, sorted by due date, filterable by priority, case, and status.

---

### 5.3 Contact Management

Every person or entity connected to a case is a contact.

#### 5.3.1 Contact Record

| Field | Type | Notes |
|---|---|---|
| `contact_id` | UUID | |
| `contact_type` | Enum | `client`, `defendant`, `insurance`, `medical_provider`, `attorney`, `expert`, `court`, `other` |
| `name` | String | Full name or entity name |
| `first_name` | String | Nullable (individuals) |
| `last_name` | String | Nullable (individuals) |
| `company` | String | Nullable |
| `email` | String | |
| `phone_primary` | String | |
| `phone_secondary` | String | Nullable |
| `fax` | String | Nullable |
| `address` | JSON | Street, city, state, zip |
| `dob` | Date | Nullable (clients) |
| `ssn_last4` | String | Nullable, encrypted |
| `notes` | Text | Freeform |
| `linked_cases` | FK[] → Case | Cases this contact appears on |
| `created_at` | Timestamp | |

Contacts are firm-wide, not case-specific. The same contact (e.g., an insurance adjuster) can be linked to multiple cases.

---

### 5.4 Document Management

#### 5.4.1 Document Upload & Storage

- Users can upload documents to any case via drag-and-drop or file picker
- Supported file types: PDF, DOCX, XLSX, JPG, PNG, MP3, MP4, and other common formats
- Files are stored in AWS S3 with server-side encryption (SSE-S3 minimum; SSE-KMS preferred)
- Each upload auto-generates a `document_upload` note attached to the case
- Maximum file size: 500 MB per file (configurable)

#### 5.4.2 Document Record

| Field | Type | Notes |
|---|---|---|
| `document_id` | UUID | |
| `case_id` | FK → Case | |
| `uploaded_by` | FK → User | |
| `uploaded_at` | Timestamp | |
| `filename` | String | Original filename |
| `file_type` | String | MIME type |
| `file_size_bytes` | Integer | |
| `s3_key` | String | Internal reference — not exposed via API |
| `category` | Enum | `medical_record`, `police_report`, `correspondence`, `pleading`, `evidence`, `contract`, `other` |
| `description` | String | User-provided description |
| `version` | Integer | Default 1; incremented on re-upload of same document |
| `tags` | String[] | |
| `ai_processed` | Boolean | Whether AI has analyzed this document |
| `ai_summary` | Text | Nullable — AI-generated summary |

#### 5.4.3 Document List

Per-case document list with:
- Filter by category, type, uploaded by, date range
- Search by filename, description, tag
- Bulk download (zip)
- Version history per document

---

### 5.5 User & Access Management

#### 5.5.1 Users

| Field | Type |
|---|---|
| `user_id` | UUID |
| `email` | String (unique) |
| `full_name` | String |
| `role` | Enum |
| `firm_id` | FK → Firm |
| `is_active` | Boolean |
| `last_login` | Timestamp |
| `created_at` | Timestamp |

#### 5.5.2 Roles & Permissions

| Role | Capabilities |
|---|---|
| `admin` | Full access; user management; firm configuration |
| `attorney` | Full case access; can close/archive cases; can approve AI drafts |
| `paralegal` | Full case access; cannot close/archive; cannot manage users |
| `case_manager` | Full case access (same as paralegal) |
| `intake` | Create new cases; edit intake fields; limited note access |
| `readonly` | View only; no create/edit/delete |
| `ai_agent` | Programmatic-only role; API/CLI access; no UI login |

Row-level security: staff only see cases assigned to them or their team, unless they have `admin` or `attorney` role with firm-wide access (configurable).

#### 5.5.3 Authentication

- Email + password (bcrypt hashed)
- MFA (TOTP — Google Authenticator / Authy) — required for `admin` and `attorney` roles
- Session tokens (JWT, short-lived with refresh tokens)
- SSO (SAML 2.0 / OIDC) — post-MVP

---

### 5.6 Frontend UI

#### 5.6.1 Navigation Structure

```
Sidebar
├── Dashboard (My Tasks, Recent Cases, Alerts)
├── Cases
│   ├── All Cases
│   ├── My Cases
│   └── [Saved Filters]
├── Contacts
├── Calendar
├── Documents
├── Reports (post-MVP)
└── Settings (admin only)
```

#### 5.6.2 Case Detail Page

The case detail page is the primary working view. Layout:

```
Case Header Bar
  Case name | Case number | Status badge | Phase badge | SOL date | Assigned team

Tab Bar
  Overview | Notes & Activity | Documents | Contacts | Timeline

Overview Tab
  Two-column layout:
  Left: Case metadata fields (all PI fields, editable inline)
  Right: Pinned notes | Upcoming tasks | Upcoming court dates

Notes & Activity Tab
  Filter/sort bar (type, date, assignee, tag)
  Note list (timeline view default)
  Compose new note button (opens inline compose panel with type selector)

Documents Tab
  Upload zone + document list with filters

Contacts Tab
  Linked contacts with role labels; add existing or create new

Timeline Tab
  Read-only chronological audit trail of all system events and status changes
```

#### 5.6.3 UI/UX Principles

- Fast: case list and case detail must load in < 1s on a standard connection
- Keyboard-navigable: power users should not need a mouse for core workflows
- Mobile-responsive: attorneys need to view cases and add notes from phone
- No modal hell: actions happen inline or in slide-over panels, not blocking modals
- Dense but not cluttered: information density should match what legal staff actually need — not a simplified consumer UI

---

### 5.7 REST API

#### 5.7.1 Design Principles

- RESTful, JSON, versioned at `/api/v1/`
- All endpoints require authentication (Bearer token)
- Pagination on all list endpoints (cursor-based)
- Consistent error response format: `{ error: { code, message, details } }`
- Full OpenAPI 3.0 spec published and kept in sync with implementation

#### 5.7.2 Core Endpoint Groups

| Group | Base Path | Description |
|---|---|---|
| Auth | `/api/v1/auth` | Login, logout, refresh, MFA |
| Cases | `/api/v1/cases` | CRUD for case records |
| Notes | `/api/v1/cases/{id}/notes` | CRUD for notes on a case |
| Documents | `/api/v1/cases/{id}/documents` | Upload, list, retrieve, delete |
| Contacts | `/api/v1/contacts` | CRUD for contacts |
| Users | `/api/v1/users` | User management (admin only) |
| Tasks | `/api/v1/tasks` | Global task list (cross-case) |
| Search | `/api/v1/search` | Full-text search across cases, notes, contacts |
| Webhooks | `/api/v1/webhooks` | Register/manage event webhooks |
| AI | `/api/v1/ai` | Trigger AI actions (draft, summarize, extract) |

#### 5.7.3 Webhook Events

The system emits webhook events for all significant state changes, enabling external integrations without polling:

- `case.created`, `case.updated`, `case.status_changed`, `case.closed`
- `note.created`, `note.updated`, `task.completed`
- `document.uploaded`
- `sol.alert` (fired at configured intervals before SOL)

---

### 5.8 Command Line Interface (CLI)

The CLI is a first-class interface — not an afterthought. It is the primary interface for AI agents and power users automating workflows.

#### 5.8.1 CLI Design

- Built with Python (Click or Typer)
- Authenticates via API key (generated in user settings — `ai_agent` role)
- All output is machine-readable JSON by default; `--pretty` flag for human-readable
- Installable via `pip install ghostops-cli`

#### 5.8.2 Core CLI Commands

```bash
# Case management
ghostops cases list [--status] [--phase] [--assigned-to] [--limit]
ghostops cases get <case_id>
ghostops cases create --name --practice-area --client-id
ghostops cases update <case_id> --field value
ghostops cases set-status <case_id> <status>
ghostops cases set-phase <case_id> <phase>

# Notes
ghostops notes list <case_id> [--type] [--assigned-to] [--since]
ghostops notes get <note_id>
ghostops notes create <case_id> --type --title --body [--due-date] [--assigned-to]
ghostops notes complete <note_id>
ghostops notes update <note_id> --field value

# Documents
ghostops documents list <case_id>
ghostops documents upload <case_id> --file <path> --category
ghostops documents get <document_id> --output <path>

# Contacts
ghostops contacts list [--type] [--name]
ghostops contacts get <contact_id>
ghostops contacts create --type --name --email --phone

# Tasks (global)
ghostops tasks list [--assigned-to] [--priority] [--due-before]
ghostops tasks complete <note_id>

# AI actions
ghostops ai draft <case_id> --template <template_name> --output <path>
ghostops ai summarize <document_id>
ghostops ai extract <document_id> --schema <schema_name>

# Search
ghostops search "<query>" [--type cases|notes|contacts] [--limit]
```

---

### 5.9 AI & LLM Integration

AI capabilities are a first-class feature — not a bolt-on. All AI actions are auditable and require an attorney review step before any output is used in an official context.

#### 5.9.1 Document Drafting

AI can generate first drafts of standard legal documents using case data:

| Template | Description |
|---|---|
| `demand_letter` | Demand letter to insurance carrier using case facts, medical summary, and damages |
| `medical_records_request` | HIPAA-compliant records request letter to treating provider |
| `client_status_letter` | Update letter to client summarizing case status |
| `settlement_breakdown` | Itemized settlement disbursement summary |
| `lien_negotiation_letter` | Letter to lien holder requesting reduction |

Draft generation process:
1. User (or AI agent) calls `ghostops ai draft <case_id> --template demand_letter`
2. System pulls relevant case fields, contact data, and note history
3. LLM generates draft
4. Draft is saved as a `note_type: ai_draft` note, status `pending_review`
5. Assigned attorney receives task to review and approve
6. Once approved, draft is saved as a document

#### 5.9.2 Document Analysis

AI can analyze uploaded documents and return structured data:

- **Medical record summarization** — extract diagnosis, treatment dates, providers, and total billed from medical records
- **Police report extraction** — extract incident date, location, parties, officer, report number
- **Insurance document parsing** — extract policy limits, coverage types, effective dates

Extracted data can be auto-populated into case fields (with attorney confirmation) or saved as a structured note.

#### 5.9.3 AI Agent Access Model

AI agents (e.g., an autonomous workflow agent) authenticate with an `ai_agent` role API key and interact entirely through the API or CLI. Agents can:

- Read any case, note, or document they have permission to access
- Create notes (tasks, call logs, general notes, ai_drafts)
- Upload documents
- Update case fields (within permission scope)
- Trigger AI drafts and extractions
- Mark tasks complete

Agents **cannot** (without attorney approval):
- Close or archive cases
- Delete notes or documents
- Change case status to any closed state
- Approve AI drafts

All agent actions are flagged `system_generated: true` in the note record and appear distinctly in the case timeline.

---

### 5.10 Search

Full-text search across:
- Case names, numbers, descriptions
- Note titles and bodies
- Contact names, emails, phone numbers
- Document filenames and descriptions

Search is powered by PostgreSQL full-text search (MVP) with a path to Elasticsearch if scale demands it.

Results are ranked by relevance and recency. Each result shows type, case link, and a content snippet.

---

## 6. Technical Architecture

### 6.1 Stack

| Layer | Technology | Rationale |
|---|---|---|
| Cloud | AWS | Compliance posture, breadth of managed services, JC familiarity |
| Backend | Python / FastAPI | FastAPI preferred over Flask: async support, auto OpenAPI generation, better for API-first design |
| Database | PostgreSQL (AWS RDS) | Relational integrity for case data; JSONB for custom fields; proven at scale |
| File Storage | AWS S3 | Encrypted at rest; presigned URLs for secure client access |
| Search | PostgreSQL FTS → Elasticsearch | Start with PG FTS; migrate if needed |
| Auth | Custom JWT + AWS Cognito (optional) | JWT for API; Cognito for managed MFA/SSO if needed |
| Background Jobs | AWS SQS + Celery | Async tasks: AI processing, document analysis, notifications |
| Notifications | AWS SES (email) + SNS (push/SMS) | SOL alerts, task reminders, system notifications |
| Frontend | React + TypeScript | Modern, component-based; matches engineer availability |
| CLI | Python / Typer | Clean API; auto-generates help docs |
| Containerization | Docker + AWS ECS (Fargate) | Serverless containers; scales to zero; no EC2 management |
| CI/CD | GitHub Actions | Standard; integrates with AWS deployment |
| Secrets | AWS Secrets Manager | No secrets in env vars or code |
| Monitoring | AWS CloudWatch + Sentry | Infrastructure + application error tracking |

### 6.2 Infrastructure Design

```
Internet
  └── AWS Route 53 (DNS)
        └── AWS CloudFront (CDN + WAF)
              ├── S3 (static frontend assets)
              └── AWS ALB (Application Load Balancer)
                    └── ECS Fargate (FastAPI containers)
                          ├── AWS RDS PostgreSQL (primary + read replica)
                          ├── AWS ElastiCache Redis (session cache, rate limiting)
                          ├── AWS S3 (document storage)
                          ├── AWS SQS (job queue)
                          └── AWS Secrets Manager
```

### 6.3 Environments

| Environment | Purpose |
|---|---|
| `local` | Developer laptop (Docker Compose) |
| `dev` | Shared development environment; auto-deployed on merge to `main` |
| `staging` | Production mirror; used for QA and client demos |
| `production` | Live system |

### 6.4 Multi-Tenancy

The system is multi-tenant from day one. Every database record includes a `firm_id` foreign key. Row-level security (RLS) in PostgreSQL enforces tenant isolation at the database level — not just the application level. This is non-negotiable.

---

## 7. Compliance & Security

### 7.1 Legal Data Handling (US)

Legal data is not technically subject to HIPAA unless the firm is a covered entity or business associate, but PI firms handle sensitive medical records under attorney-client privilege and state bar confidentiality rules. Requirements:

- All data encrypted at rest (AES-256) and in transit (TLS 1.2+)
- Encryption keys managed via AWS KMS
- Data residency: US-only (no cross-border data transfer)
- Data retention and deletion policies configurable per firm
- Right to deletion: firm data can be fully purged on contract termination
- No data used for model training without explicit opt-in

### 7.2 Audit Logging

Every write operation is logged:

| Field | Value |
|---|---|
| `timestamp` | UTC |
| `actor_id` | User or agent ID |
| `actor_type` | `user` / `ai_agent` / `system` |
| `action` | `create` / `update` / `delete` / `status_change` |
| `resource_type` | `case` / `note` / `document` / etc. |
| `resource_id` | UUID |
| `diff` | JSON diff of changed fields (before/after) |
| `ip_address` | Request IP |

Audit logs are immutable — write-once, stored in a separate append-only table (or AWS CloudTrail for infrastructure events).

### 7.3 SOC 2 Readiness (Target: Type II post-MVP)

Controls to implement from day one:

- **CC6** — Logical access controls (roles, MFA, least privilege)
- **CC7** — System operations (monitoring, incident response)
- **CC8** — Change management (CI/CD with approval gates)
- **CC9** — Risk mitigation (vendor review, backups)
- **A1** — Availability (uptime monitoring, SLA targets)
- **C1** — Confidentiality (encryption, access controls, data classification)

### 7.4 Availability Targets

| Environment | Uptime Target |
|---|---|
| Production | 99.9% (< 8.7 hrs/year downtime) |
| Staging | Best effort |

Achieved via: multi-AZ RDS deployment, ECS Fargate auto-scaling, CloudFront CDN, automated health checks and failover.

### 7.5 Backup & Recovery

- RDS automated backups: daily snapshots, 30-day retention
- Point-in-time recovery enabled
- S3 versioning enabled on document bucket
- Recovery time objective (RTO): < 4 hours
- Recovery point objective (RPO): < 1 hour

---

## 8. Integrations

### 8.1 Strategy

All external integrations are mediated through the GhostOps API. There is no direct database access granted to third parties. Integration points:

1. **Webhooks (outbound)** — GhostOps pushes events to external systems
2. **REST API (inbound)** — External systems push data to GhostOps
3. **Native connectors (post-MVP)** — Pre-built integrations with specific platforms

### 8.2 Target Integrations (Roadmap)

| Integration | Type | Priority |
|---|---|---|
| FileVine | Data import / migration | High |
| Clio | Data import / migration | High |
| LeadDocket | Data import / migration | Medium |
| SmartAdvocate | Data import / migration | Medium |
| RingCentral | Call logging (inbound events → call log notes) | High |
| Twilio | SMS notifications to clients | Medium |
| DocuSign | Document signing workflow | Medium |
| Google Calendar | Sync court dates and calendar events | Medium |
| Outlook / Exchange | Email logging | Medium |
| QuickBooks | Trust accounting / disbursement tracking | Low |
| Zapier / Make | General automation via webhook | Low |

### 8.3 Data Migration

Migration from legacy systems is a critical GTM requirement. The migration tooling must:

- Accept data exports in the legacy system's native format (CSV, JSON, XML)
- Map legacy fields to GhostOps schema
- Preserve document attachments (download and re-upload to S3)
- Log all migration events and flag records that need manual review
- Be runnable via CLI: `ghostops migrate --source filevine --input ./export/`
- Be idempotent (safe to re-run without duplicating data)

---

## 9. Phased Delivery Plan

### Phase 1 — MVP ("The Bones")

**Goal:** A working CMS that a PI firm can actually use day-to-day.

**Scope:**
- [ ] User authentication (email/password + MFA)
- [ ] Firm and user management
- [ ] Case record with PI metadata template
- [ ] Case status and phase model (default PI phase set, fixed)
- [ ] SOL tracking and alerts
- [ ] Note system (all core types)
- [ ] Task management + My Tasks view
- [ ] Contact management
- [ ] Document upload and storage (S3)
- [ ] Case list with filter/sort/search
- [ ] Case detail page (all tabs)
- [ ] REST API (full coverage of above)
- [ ] CLI (core commands)
- [ ] AWS infrastructure (ECS, RDS, S3, SES)
- [ ] Audit logging
- [ ] Basic role-based access control

**Not in MVP:**
- Custom phase management (add, rename, reorder, deactivate phases)
- SSO / SAML
- AI drafting and document analysis
- Third-party integrations (except webhook scaffolding)
- Data migration tooling
- Reporting / analytics
- Client portal
- Mobile native app

---

### Phase 2 — AI & Automation

**Goal:** Layer in AI capabilities that save legal staff hours per case.

**Scope:**
- [ ] AI document drafting (demand letter, records request, client letter)
- [ ] Medical record summarization
- [ ] Police report extraction
- [ ] AI draft review/approval workflow
- [ ] AI agent role + programmatic access hardening
- [ ] Background job infrastructure (SQS + Celery)
- [ ] Webhook system (outbound events)

---

### Phase 3 — Integrations & Migration

**Goal:** Make it easy for firms to switch to GhostOps from legacy platforms.

**Scope:**
- [ ] FileVine data migration tooling
- [ ] Clio data migration tooling
- [ ] RingCentral call log integration
- [ ] Google Calendar sync
- [ ] DocuSign integration
- [ ] Zapier / Make webhook support
- [ ] Custom phase management (add, rename, reorder, deactivate)

---

### Phase 4 — Scale & Compliance

**Goal:** Harden the system for growth and achieve formal compliance certifications.

**Scope:**
- [ ] SOC 2 Type II audit preparation and certification
- [ ] SSO / SAML 2.0
- [ ] Elasticsearch migration (if needed)
- [ ] Reporting and analytics dashboard
- [ ] Client portal (read-only case status for clients)
- [ ] Multi-AZ full redundancy hardening
- [ ] SLA monitoring and uptime dashboard

---

## 10. Open Questions

These items require a decision before or during MVP development:

| # | Question | Status |
|---|---|---|
| 1 | Flask vs FastAPI for backend? | **Recommendation: FastAPI** — async, auto OpenAPI, better DX |
| 2 | Custom JWT auth vs AWS Cognito? | Lean toward custom JWT for MVP; Cognito for SSO later |
| 3 | Which LLM provider for AI features? | OpenAI GPT-4o or Anthropic Claude — evaluate on demand quality |
| 4 | Elasticsearch now or PG FTS first? | PG FTS for MVP; revisit at 10k+ cases |
| 5 | Self-hosted vs SaaS (multi-tenant) model? | SaaS multi-tenant — single deployment, per-firm data isolation |
| 6 | Pricing model? | Outside scope of PRD — needs separate business doc |
| 7 | Custom field storage: JSONB vs EAV table? | **Recommendation: JSONB** — simpler, indexed, PostgreSQL native |
| 8 | Which LeadDocket and SmartAdvocate export formats are available? | Needs discovery with target firm |

---

## Next Steps

- [ ] Review and approve this PRD
- [ ] Resolve open questions (see §10)
- [ ] Define PI metadata field template (finalize all field names, types, enums)
- [ ] Create system data model diagram (ERD)
- [ ] Create AWS architecture diagram
- [ ] Set up GitHub repo and project board
- [ ] Begin Phase 1 development sprint planning
