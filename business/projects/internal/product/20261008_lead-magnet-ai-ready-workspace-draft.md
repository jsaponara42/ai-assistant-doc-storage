---
title: "Lead Magnet Draft — The AI-Ready Workspace (Free Starter Guide)"
date: 2026-10-08
tags: [marketing, offer, ai, idea]
ai: claude
status: needs-attention
---

# Lead Magnet Draft: The AI-Ready Workspace

## Summary
A first draft of the free lead magnet (decision AD-041), simplified from [[business/projects/internal/product/20261008_ai-native-operating-architecture]]. It gives away the shape and the rules: Notion for drafts and Drive for finals, IDs, naming, a 4-database starter set, the summary trick, plain-language AI rules, and a manual backup habit. It keeps the build, the full ten-database system, per-firm taxonomy, skills, scripted backup and governance paid. Ready for JC's edit, then design (brand guidelines) and a format decision (PDF, Notion template, or both).

## Context
- **Pattern:** same reciprocation mechanic as [[business/projects/internal/product/20260818_File_Taxonomy_Free_Tier_Principles]]. Give away the rules; sell the implementation and the upkeep.
- **Audience (assumed):** owners and ops leads of small service firms (consultancies, fractional operators, agencies) who use Google Drive and are starting to use AI assistants. `[TO CONFIRM with JC]`
- **No client names.** The numbers come from Blue Tusk's own tests.
- **Open decisions** are at the end.

---

## Content (the guide, as the reader sees it)

# The AI-Ready Workspace
### A free starter guide to setting up your files so AI helps instead of costing you

You've started using AI to draft documents, summarize calls and keep track of clients. Then you hit one of three walls:
- **It costs more than it should.**
- **It can't find the right file.**
- **It mixes up one client with another.**

Usually the AI isn't the problem. The workspace it's working in is. It was built for people, and AI works differently.

This guide covers the rules we use to set up workspaces for AI. You can apply all of them yourself, starting this week.

---

## 1. Why AI gets expensive in Google Docs

AI tools pay by the amount of text they read and write, counted in "tokens." Here's what we found when we measured it:

- **Reading what a Google Doc says** is cheap, about the same as the text itself.
- **Editing one sentence in the middle of a Google Doc** is expensive. Before the AI can change anything, it has to read the document's full structure, including every font, style and spacing setting on every paragraph. **In our tests, one small edit cost about 20,000 tokens.**
- **The same edit in Notion cost about 100 tokens.**

Do that a few hundred times a month, across every draft and every revision, and the difference adds up quickly.

**The fix isn't to stop using Google. It's to stop drafting in it.**

---

## 2. Rule one: drafts in Notion, finals in Drive

| | Notion | Google Drive |
|---|---|---|
| **What lives here** | Every draft, your notes on each client and project, your contact list, your tasks | Finished documents, files clients send you, signed contracts |
| **Who works here** | You, your team, and AI, constantly | Clients and partners; AI only to publish a finished file |
| **Why** | Cheap to edit, easy to search, every item has dates and status built in | It's what clients expect; easy to share and sign |

The flow:
1. **Draft in Notion.** Revise as many times as you like. It's cheap.
2. **When it's ready**, create the Google Doc once, in the right folder.
3. **The Google Doc is now the final.** Make only small changes to it from here.

Bonus: because every Notion item records when it was created and last edited, you get a timeline of everything you've worked on for free. Ask your AI "what did I work on yesterday?" and it can actually answer.

---

## 3. Rule two: one ID for every client and project, used everywhere

AI gets confused when the same client is "Acme" in one place, "Acme Corp" in another and "AC-2026" in a third. Give each one **a single ID** and use it everywhere: folder names, file names, your task list, your invoices.

**A simple scheme:**
- **Client code:** 3 capital letters, never reused. `ACM`
- **Project ID:** client code + start date + a two-digit counter. `ACM-26100801` (project 01, started Oct 8, 2026)

**Why it works:**
- The project ID **tells you, and your AI, which client folder to open.** No searching required.
- Searching `ACM-` finds every project you've ever done for that client.
- An AI working on `ACM-26100801` knows to stay inside Acme's folder and nobody else's.

---

## 4. Rule three: name files by who will see them

**Internal files** get a structured name that sorts by date:
`20261008_ACM-26100801_Meeting-Notes`

**Anything a client will see** gets a clean title:
`Q4 Operations Plan`

When you share a Google Doc, the client sees its file name in the header, the browser tab and Google's share email. Don't make them read your internal codes. The date and ID still live in the folder name, so nothing is lost.

---

## 5. The starter set: four Notion databases

You don't need a complicated system to start. Four linked databases cover most of it:

| Database | One row per… | Key fields |
|---|---|---|
| **Companies** | Client or partner | Client code, status, notes about the client, link to their Drive folder |
| **People** | Contact | Company, email, role, last contacted, next follow-up |
| **Projects** | Piece of scoped work | Project ID, company, stage, main contact, link to the project folder |
| **Tasks** | To-do | Project, owner, due date, status |

**Link them:** each Person belongs to a Company, each Project belongs to a Company, and each Task belongs to a Project.

**Start your pipeline with People, not Projects.** Put prospects in People with a stage (reached out → in conversation → opportunity) and a next follow-up date. Only create a Project when there's real work to scope. Your project list stays clean, and you'll never lose a warm lead.

---

## 6. The summary trick

Add **one field to every database: Summary.** It's a single line, kept up to date, saying what this item is and where it stands.

When your AI looks across your workspace, it can read hundreds of one-line summaries for about the cost of opening a single long document. That's how "catch me up on this week" becomes fast and cheap instead of slow and expensive.

Add a **Needs Attention** checkbox next to it, and you have an instant "what's open" view for you and your AI.

---

## 7. Ten rules to give your AI

Copy these into your AI assistant's instructions, or into a "how we work" page it reads first.

1. **Stay inside one client.** When working on a client, use only that client's folder and notes. Never mix clients.
2. **Find things by ID, not by searching everything.** Use the client code and project ID.
3. **Draft in Notion. Create the Google Doc only when it's ready.**
4. **Edit finished Google Docs only in small ways:** swap a phrase or add to the end. No big rewrites.
5. **Read a long file once, then write a summary.** Use the summary next time.
6. **Keep the Summary field current** whenever you change something meaningful.
7. **Never send anything to a client, partner or prospect without a person approving it.**
8. **Never touch money:** no marking invoices paid, no changing amounts.
9. **Label your work.** Start comments in shared documents with "AI:" so people know who wrote them.
10. **Don't change the system itself** (fields, databases, folder structure) without explicit approval.

---

## 8. Your Notion export is not a backup

Notion keeps your work safe on its servers, but:
- **The built-in export is manual.** The download link expires after a few days.
- **An export can't simply be re-uploaded to rebuild your workspace.** The links between your databases come out as plain text.
- **Trash and page history only go back so far,** and they're inside Notion, so they're no help if you lose access.

**The minimum habit:** once a month, export your whole workspace as Markdown & CSV, **download it the same day**, and keep it somewhere outside Notion.

That protects your content. Rebuilding the *connections* between your databases is a bigger job.

---

## What this guide doesn't cover

This guide gives you the shape of an AI-ready workspace. It doesn't build it for you. Here's where most firms get stuck:

- **Fitting it to how your firm actually works.** Every firm's mess is different. Mapping years of files, trackers and habits onto a clean structure is judgment work.
- **The full system.** Beyond the starter four: drafts, meeting notes, client documents, contracts, invoices and company knowledge, with the right permissions so sensitive information stays restricted.
- **Making the AI follow the rules every time.** Rules in a document get forgotten. Built-in skills don't.
- **Real backups.** Automatic, scheduled exports that preserve every link between your databases, with tested restores.
- **Keeping it from drifting.** Systems decay the moment nobody is minding them: one exception becomes two, then chaos.

**That's what we do at Blue Tusk.** If you'd like help setting this up for your firm, [book a call / CTA].

---

## Open decisions (for JC)
1. **Format:**
   - A designed PDF (brand guidelines).
   - A **duplicable Notion template** of the four-database starter set.
   - Both. A template is very concrete and shows the product, but it gives away more.
2. **Audience and title:** confirm the target reader. Alternative titles:
   - "Your AI Can't Afford Your Google Drive"
   - "The AI-Ready Workspace"
   - "Stop Drafting in Google Docs"
3. **How specific the numbers should be.** "About 20,000 vs about 100 tokens" is a strong hook but comes from a small internal test. Options: keep it with "in our tests", or soften it to "over 100x cheaper."
4. **CTA:** book a call vs a paid "AI-Ready Workspace" setup offer vs pairing it with the Workflow Waste Snapshot.
5. **Gating:** an email-gated download vs open publishing, plus a LinkedIn post series built from it (one post per rule).
6. **Overlap with the free-tier taxonomy guide:**
   - Merge into one guide, or
   - Keep two (taxonomy = "how to organize files"; this one = "how to make it work with AI") with cross-links.
