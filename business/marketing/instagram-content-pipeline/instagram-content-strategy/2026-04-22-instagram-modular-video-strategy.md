---
title: "Instagram Modular Video Strategy"
date: 2026-04-22
tags: [strategy, project, ai]
ai: claude
status: needs-attention
---

## Summary
A modular video content system for Instagram where individual hooks, middles, and CTAs are filmed once and stitched together programmatically to produce many unique videos from a small number of shoots.

## Context
JC wants to build a scalable Instagram content pipeline targeting personal injury lawyers. The core insight is that filming modular parts — hooks, meat, CTAs — then combining them systematically produces far more content per shoot than filming full videos.

## Content

### The Strategy

Film three types of clips in a single session:

**Hooks (10–15 clips)**
Call out a specific audience type or pain point. These are the opening seconds that stop the scroll. Broadly written so they work with any middle section.

**Middle / Meat (10 clips)**
The core content — insight, story, or value delivery. Each should stand alone topically.

**CTAs / Outros (5 clips)**
Closing calls to action. Examples: follow for more, DM if this resonates, check the website link.

### The System

- Each category lives in its own folder on-device
- A program stitches them methodically (not randomly) — every hook pairs with every middle, every middle pairs with every CTA
- Result: if you film 10 hooks × 10 middles × 5 CTAs = 500 unique video combinations from one shoot session

### Production Requirements

- Must wear the same shirt across all clips (visual consistency)
- Same background/location for all clips
- Film everything in one session (continuity)

---

## Tool Strategy

### Goal
After clips are filmed and trimmed, the workflow should be as close to zero steps as possible. Drop files in, run one thing, get a folder of finished videos.

### Folder Structure

```
/batch-1/
  /hooks/
    hook-01.mp4
    hook-02.mp4
    ...
  /meats/
    meat-01.mp4
    meat-02.mp4
    ...
  /ctas/
    cta-01.mp4
    cta-02.mp4
    ...
  /output/
    (generated videos land here)
```

Everything is driven by folder contents. No config file, no manual list — the script reads whatever is in each folder and works with what it finds.

### What the Script Needs to Do

1. **Read** the three input folders and collect all `.mp4` files in each
2. **Generate combinations** — every hook × every meat × every CTA, in order
3. **Concatenate** each combination into a single video: hook → meat → CTA
4. **Name the output** clearly: `hook-01_meat-03_cta-02.mp4` so each file is traceable back to its parts
5. **Write** all outputs to `/output/`

### Technical Approach

Use **ffmpeg** via Python subprocess rather than a video editing library. Since all clips are filmed in one session with the same camera settings, they share identical encoding — ffmpeg can concatenate them with a concat demuxer (no re-encoding), which is near-instant and lossless.

No quality loss. No slow render times. Just file assembly.

Dependencies: Python 3, ffmpeg installed on the system (available via `brew install ffmpeg` or the ffmpeg website).

### Generating a Subset (Optional)

500 videos at once is rarely needed. The script should support an optional mode where you pass a specific combination — e.g. `--hook 1 --meat 3 --cta 2` — to generate a single video on demand. Useful for testing or for scheduling specific pairings.

### Workflow After Filming

1. Film and trim all clips in your video editor of choice
2. Drop trimmed clips into the correct folder (`/hooks/`, `/meats/`, `/ctas/`)
3. Run the script: `python stitch.py`
4. Open `/output/` — all combinations are there, named and ready to schedule

That's it. No other steps.

### Future Additions (Low Priority)

- A simple text file or CSV that maps clip filenames to their script titles — useful when picking which videos to post
- A `--limit N` flag to generate only N random combinations rather than all of them
- Auto-resize output to Instagram's preferred aspect ratio if source clips aren't already 9:16

---

## Next Steps
- [x] Write hook scripts (10–15 variations targeting PI lawyer pain points)
- [x] Write middle content scripts (10 topics)
- [x] Write CTA scripts (5 variations)
- [ ] Build the stitch script (`stitch.py`)
- [ ] Plan a filming session (same day, same outfit, same background)
- [ ] Film and trim all clips into the folder structure above
