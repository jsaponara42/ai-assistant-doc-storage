---
title: "Writing Conventions"
date: 2026-04-17
tags: [strategy, tool]
ai: claude
status: ok
---

# Writing Conventions — Blue Tusk Marketing / Writing

This file governs how post drafts are created and structured in this folder. Read it before creating or editing any post file.

---

## Frontmatter

Every post file requires this frontmatter block at the top. Use the following schema exactly:

```yaml
---
title: "Post: [Human-readable title of the post]"
date: YYYY-MM-DD
tags:
  - strategy
  - idea
ai: claude
status: needs-attention
platforms:
  - linkedin
---
```

### Field notes

| Field       | Rules                                                                                                                                 |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `title`     | Always prefix with `"Post: "` followed by the post title as it would appear publicly. Use the actual working title, not the filename. |
| `date`      | Creation date. Do not update on edits.                                                                                                |
| `tags`      | Use existing tags from the vault tag vocabulary. Default for post drafts: `strategy`, `idea`.                                         |
| `ai`        | Set to `claude` if AI wrote or drafted it. Set to `human` if JC wrote it without AI assistance.                                       |
| `status`    | `needs-attention` = draft, not ready to publish. `ok` = reviewed and approved. `archived` = published or abandoned.                   |
| `platforms` | List of intended publishing platforms. Default: `linkedin`.                                                                           |
| `posted?`   | `ye`                                                                                                                                  |

---

## File naming

`post-{category}-{short-description}.md`

- All lowercase, hyphen-separated
- Category matches one of the six post categories (see `00_linkedin-post-ideas.md`)
- Short description is 2–4 words, kebab-case
- No date prefix — post files are not time-stamped by default

**Examples:**
- `post-story-voice-notes-ai.md`
- `post-ht-real-ai-is-boring.md`
- `post-ge-ai-tool-poll.md`

---

## File structure

Every post file follows this section order:

```
[frontmatter]

## Draft

[the post body — ready to copy-paste to LinkedIn]

---

[closing question or CTA, italicized]

---

## Notes

[editorial notes for JC — things to review, decisions made, cut content, sequencing dependencies]

---

# Original Transcript

[raw voice note or source material — preserved in full, never edited]
```

### Section rules

- **Draft** — the post as it will be published. No markdown headers inside the post body itself. Bold is fine for scannable structure. Keep under 300 words for LinkedIn.
- **Notes** — for JC's eyes, not the post. Flag: sequencing dependencies on other posts, things to cut, tone concerns, length warnings.
- **Original Transcript** — always preserved verbatim at the bottom if a voice note was the source. Never clean it up.

---

## Style

All post copy follows the style guide in `WRITING-STYLE.md`. The short version:

- No em-dashes. Use a period or a comma.
- No rule of three. One strong word beats three weak ones.
- No elegant variation. Use the same word twice rather than rotating synonyms.
- No negative parallelisms ("it's not X, it's Y").
- Plain copulas. "Is" and "are" over "serves as", "represents", "features".
- Banned words include: key, crucial, pivotal, highlight, showcase, valuable, enhance, landscape, tapestry, underscore, delve. See full list in `WRITING-STYLE.md.md`.
- Voice: peer-to-peer. A person talking to someone they respect, not a brand talking at a feed.

---

## Workflow

1. JC drops a voice note or brief into the post file under `# Original Transcript`
2. Agent reads the transcript, reads this file and `WRITING-STYLE.md`, then writes the `## Draft` section
3. Agent sets `status: needs-attention` in frontmatter
4. JC reviews, edits the file directly, then sets `status: ok` when approved
5. After publishing, JC sets `status: archived` and checks off the entry in `00_linkedin-post-ideas.md`
