# Client project structure (agent reference)

> Read this only when creating/organizing files inside `business/projects/client-projects/`.
> Based on the Maycomb Capital project — the standard for all client projects going forward.

## Project folder
`business/projects/client-projects/YYMMDDNN_client-kebab-name/`
- `YYMMDD` = engagement start date, `NN` = sequence (usually `01`)
- e.g. `26061601_maycomb-capital`

## Required subfolders (create all three for every new client project)
- `call-prep/` — call briefs, prep docs for upcoming calls
- `client-facing-deliverables/` — anything sent to the client (SOW, playbooks, roadmaps, presentation outlines)
- `SOPs/` — one file per client process documented

## Root of project folder (not in a subfolder)
- Discovery brief, workflow map, outstanding-questions tracker, internal roadmap
- No `overview.md` for client projects — the discovery brief serves that role instead

## File naming
`YYYYMMDD_Title_Case_With_Underscores.md`
- `xx_` prefix = internal-only, never shown to client (e.g. `xx_Maycomb_AI_Automation_Roadmap_INTERNAL.md`)
- Outstanding-questions tracker: `xx_outstanding-questions.md` while open → rename to `..._outstanding-questions-answered.md` (drop `xx_`) once resolved

## Placement rule
Client engagement docs never go in generic `business/projects/` — always under `business/projects/client-projects/{project-folder}/`, in the correct subfolder above.

---
*Assumption flagged:* existing Maycomb files mix dash/underscore and casing slightly. This doc standardizes on `YYYYMMDD_Title_Case_With_Underscores.md` going forward — say the word if you want a different casing rule and this file gets updated.
