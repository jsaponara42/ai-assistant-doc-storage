---
title: "Notion Migration Lessons Learned"
date: 2026-10-09
tags: [project, tool, ai, sop]
ai: notion-ai
status: complete
---

# Notion Migration Lessons Learned

> **What this is:** lessons from moving Blue Tusk's legacy Notion (CRM Master, Operations Master, Blue Tusk Meeting Notes) into the Operating System on 2026-10-09. Use it as the starting brief the next time Notion AI builds an operating system for a company. Section 6 is a copy-paste checklist.

Related: [[business/projects/internal/product/20261009_Notion_OS_migration_prompts]] (the prompts that ran this migration).

Verified by Claude 2026-10-09 (row counts queried directly): Projects 26, Tasks 187, Companies 23, People 111, Meeting Notes 59; legacy Blue Tusk Meeting Notes now holds 0 pages. JC confirmed all relations checked.

## 1. What was migrated

- **CRM Master:** became Companies (23) and People (111). 2 companies were dropped by decision, and the owner was left out of People because he is a team member.
- **Operations Master:** became Projects (26), Tasks (187) and Contracts (5). The contracts were built from the projects' revenue fields.
- **Blue Tusk Meeting Notes:** became Meeting Notes (59). The pages were moved, not copied, and 1 accidental page was deleted.
- **Records:** every row has a line in the Migration log. Unclear rows were flagged with Needs Attention and listed on the Review list. Schema changes went into the System Registry change log.

## 2. The approach that worked (keep it)

1. **Audit first, migrate second.** Build a Migration plan page covering:
    - how full each property is
    - what is in page bodies (AI meeting notes, transcripts, files, embedded databases, sub-pages, comments)
    - duplicates and relations pointing to deleted rows
    - team members
    - the proposed company and project tables
    - everything that doesn't fit
    - formulas and rollups that won't be copied
2. **Turn every open question into a numbered decision list for the owner.** Blue Tusk had 28. Getting them answered in one pass up front saved many back-and-forth turns later.
3. **Pilot 3 rows, then stop for review.** Then work in batches of 20 or fewer.
4. **Add one relation at a time and re-read after each.** Order: base properties → Project → Attendees/People → Company. Check every batch against the source before the next step.
5. **Keep a Legacy Link and a Migration log line for every row.** The log is the audit trail and makes the final check easy.
6. **Flag, don't guess.** If something is unclear, create the row anyway, tick Needs Attention, give the reason in Summary and add it to the Review list.
7. **Order of work:** CRM (companies, then people) → Operations (projects, tasks, contracts) → Meeting Notes → final check. Each database depends on the maps from the one before (old ID → new URL).

## 3. Challenges and how to avoid them next time

### Rules that contradict each other

- **"Legacy is read-only" vs "move the meeting pages":** decision 27 said move the meetings, but the migration rules said never touch legacy. This wasn't resolved until mid-task. **Next time:** before the pilot, check the owner's migration rules against the decision answers and the target schema, and ask about every conflict in one message.
- **The schema differed from what the owner remembered:** a Company relation already existed on Meeting Notes, added by an earlier decision. **Next time:** load the live target schema and quote it back before mapping.
- **Expected count vs a delete decision:** the owner expected 60 meetings, but one was approved for deletion. **Next time:** give expected counts as "X minus the rows excluded by decisions."
- **"Don't delete properties" (change protocol rule 2) vs cleanup:** the owner chose to delete duplicate columns anyway. **Next time:** ask early whether duplicates created by the migration count as an exception, and record the exception in the change log.

### Meeting notes and transcripts

- **AI meeting notes blocks can't be recreated.** No tool can create the native block with its recording, summary, notes and transcript. At best they become plain text, which is about 1.5M characters for 50 meetings, with citations still pointing at the old pages. **Default for next time: move meeting pages, don't copy them.** It keeps transcripts, comments, backlinks and history, and needs no Legacy Link because the page stays the same.
- **What a move does to properties:**
    - Properties with the same name and type carry over, and select values matched the new lowercase options with no new options created.
    - Relations that point at the old databases are dropped.
    - Old properties with no match are added to the new database as extra columns and also appear in the views.
    - The new database's default template is not applied to moved pages.
- **Before any move, save every property value and body of the source rows to files.** That snapshot was used to rebuild Date, the checkboxes and all relations, and to prove the bodies were unchanged afterwards (same text, same number of transcript paragraphs).
- **After the move:** copy the values from the extra columns into the right properties, check them on every row, then delete the extra columns. A column can't be deleted while a view still shows it, so remove it from the views first.
- **Watch for:** a meeting whose Date property disagrees with the date in its AI notes block. Keep the property value and mention it.

### Data quality patterns

- A bot account was set as Responsible on 115 rows. Reassign them to the owner.
- Statuses with no equivalent (Archived) need a mapping (cancelled). Overdue open tasks were re-dated to the migration day.
- Old projects with no "Type" (task vs project) or no status: migrate them, flag them and let the owner decide.
- Dangling relations and stray text (" ka") usually point to a real person. Ask, then link.
- Rows with neither a project nor a company: leave them unlinked and flag them.
- Several projects or companies on one meeting is normal. Make Project and Company allow several values from the start.
- 74 people with no company was fine. Don't over-clean; ask before fixing suspicious links.

### Naming and IDs

- **Project ID:** `{CLIENT CODE}-{YYMMDD}{NN}`. The date is the project's Start Date, and the NN counter restarts per client. Name = Project ID + space + clean name.
- **Clean names:** no emoji, no person or client names inside project names, and update quarter labels (Q3 → Q4). Rename catch-alls ("00_URGENT", "Non-Business") to simple internal and admin catch-all projects.
- **Select values are lowercase.** If a select was empty in the old data, leave it empty and flag it.

### Formulas, rollups and computed fields

- These are not copied. List each one with what it calculated and which old views and dashboards used it. Blue Tusk's Revenue Snapshot depended on Contract Value, Active MRR and YTD Revenue.
- Revenue fields on projects became Contracts in the restricted area. The owner wants them fed from Stripe later.
- A follow-up cadence formula was replaced by a one-time fixed Next Follow-up date per person.
- Notes and touch logs went into the person's page body. Draft message fields were dropped.

### Team members and identity

- Leave team members out of People and use the person property instead (Team Attendees, Owner).
- Confirm which email is canonical when the CRM and the Notion account differ.

## 4. Tooling lessons for the AI doing the work

- **Bulk reads:** use the `ntn` CLI (`datasources query --limit 300 --json`, `pages get --json`) and save the results to files. Page loads cut relations off at 25, so use `ntn api v1/pages/{id}` for full relation lists.
- **Transcripts:** normal page loads leave them out. `ntn api v1/blocks/{transcript_block_id}/children` returns them, and the meeting_notes block gives the summary, notes and transcript block IDs.
- **Writes:** build payloads with a script, save them to a file and pass the file to the tool. Never print large payloads.
- **Mapping:** match created rows by Legacy Link with a query instead of saving every create result.
- **A failed write may still have worked:** "output projection" errors came back on table appends that had actually succeeded. Always re-read before retrying, or you get duplicate log rows.
- **Don't run a check in parallel with the write it's checking.** The first check reported false mismatches. Run them one after the other.
- **Appending to tables (Migration log, Review list, change log):** the anchor text must be unique, so check how often it appears first. Repeated endings ("…signed copy is attached. |") failed until a value unique to that row was added.
- **Escape** square brackets, asterisks, tildes, backticks, angle brackets, dollar signs and pipes in titles and notes written into tables. Checkboxes take true/false.
- **Deleting in the UI may not stick:** a page the owner said was deleted wasn't in the trash yet. Check `in_trash` before reporting counts.
- **Safety review can block schema deletes even after the owner approves.** Explain in plain terms, get a clear go-ahead, then retry.

## 5. Things to ask the owner on day one next time

1. **Rules:** Are there overrides to the migration rules (read-only legacy, Legacy Link on every row, no deletes)? List the expected exceptions: moved meeting pages, duplicate columns created by the move.
2. **Team:** Who is on the team? Which accounts are bots? Which email is canonical?
3. **Statuses:** How do old statuses map to the new ones (including archived/cancelled)? What happens to overdue open tasks?
4. **Company types:** Which values exist (for example prospect vs opportunity)? Who should be dropped entirely?
5. **Many-to-many:** Can a meeting or task have several projects or companies?
6. **Revenue:** Where does money data live, and should formulas or dashboards be rebuilt?
7. **CRM cadence and notes:** formula or a fixed date? Should notes go into page bodies?
8. **Naming:** Project ID format, how same-day IDs are numbered, which date to use, clean-up rules.

## 6. Checklist for the next company

- [ ] Load and quote the live target schema (every database and relation). Note anything the owner may not expect.
- [ ] Run the audit and write the Migration plan with a numbered decision list. Get the answers.
- [ ] Check the rules against the decisions and the schema, and resolve every conflict before the pilot.
- [ ] Set up the Migration log, the Review list and a change-log entry. Add a Legacy Link property where rows are copied.
- [ ] Save all source properties and bodies to files (including transcripts through the API).
- [ ] CRM: companies → people. Pilot 3, stop, then batches of 20 or fewer, with a re-read after each relation.
- [ ] Operations: projects (IDs and names) → tasks → contracts. Same pilot and batch rules.
- [ ] Meetings: have the owner move the pages, then rebuild properties from the snapshot and delete the duplicate columns (remove them from views first).
- [ ] Final check: counts per database vs source minus exclusions; relation checks; spot-check 10 random rows per database; list every Needs Attention row with its reason.
- [ ] Update the registry pages, change log and quick reference. Never delete, archive or rename the legacy databases unless the owner asks.
- [ ] After the owner signs off, remove the Legacy Link properties and hide any deprecated ones.

## 7. Still open at Blue Tusk

- **Final check across all databases:** done 2026-10-09 (JC confirmed relations; Claude confirmed counts).
- **"All meetings" view:** shows Source (deprecated) and Legacy Link (empty on meetings). Hide both.
- **Review list:** open items (empty meeting types, Bill Kinnelly with no project, the SyncScript proposal set to lost vs done, the "Add contacts to CRM" task).
- **Legacy Link properties:** remove from Companies, People, Projects, Tasks and Contracts once JC signs off.
