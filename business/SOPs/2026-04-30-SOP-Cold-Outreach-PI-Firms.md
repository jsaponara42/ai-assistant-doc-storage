---
title: SOP — Cold Outreach to PI Firms
date: 2026-04-30
last-updated: 2026-04-30
tags:
  - strategy
  - sales
  - client
ai: claude
status: ok
---

# SOP — Cold Outreach to PI Firms

## Summary

The current outreach method for generating pipeline from cold PI firm contacts. The entry point is a personalized "Workflow Waste Snapshot" — a short external research report delivered by email that demonstrates specific operational gaps before asking for anything. Previous methods (generic cold email sequence via Instantly, LinkedIn voice/video outreach) produced near-zero response on ~430 contacts and have been superseded by this approach.

## Previous Methods (Superseded)

These files document the prior outreach approaches and the adversarial analysis that led to their replacement. They are kept for reference and historical context.

- Cold email sequence (v2, Instantly): [[business/sales/2026-04-14-audit-email-sequence]]
- Social outbound SOP (v3, latest): [[business/sales/2026-04-30-Social_Outbound_SOP_Free_Workflow_Waste_Audit]]
- Social outbound SOP (v2): [[business/sales/2026-04-14-Social_Outbound_SOP_Free_Workflow_Waste_Audit]]
- Social outbound SOP (v1): [[business/sales/2026-04-03-Social_Outbound_SOP_Free_Workflow_Waste_Audit]]
- Offer creation document: [[business/sales/2026-04-03-free-workflow-audit-free-offer-creation-agp]]
- Pipeline bottleneck diagnosis: [[business/research/2026-04-30-zero-response-pipeline-diagnosis]]

## Why This Method Replaced the Previous One

Cold email deliverability was confirmed working (mail-tester.com score clean, SPF/DKIM/DMARC verified). The root cause of zero response was identified as:

1. Apollo list quality — PI attorneys on Apollo have been cold emailed to saturation by legal tech vendors
2. No social proof or digital footprint — firm searched, nothing credible returned
3. Entry point required too much trust before delivering any value

The snapshot approach resolves all three: it bypasses Apollo lists (manually sourced targets), it demonstrates capability before asking for anything, and it delivers real value — a personalized external audit — before any call is booked.

---

## Current Process

### Step 1 — Source targets manually

Do not use Apollo or scraped bar directories. Source targets from:

- Google Maps search for PI firms in a target city — check which are running Google Ads (paid result = active lead flow)
- State bar directories filtered by PI specialty and admission date
- Martindale-Hubbell / Avvo filtered by firm size and specialty
- LinkedIn search for PI firm managing partners in specific metro areas

**Target profile:** PI firm, 3–15 staff, actively running paid ads or generating consistent lead flow, managing partner or office manager contactable by email.

**Volume:** Work in batches of 10–15. Do not send to more than 15 at a time until response rate is established.

### Step 2 — Generate the Workflow Waste Snapshot

Use the `pi-firm-snapshot` skill (see [[business/SKILLS/pi-firm-snapshot/SKILL.md]]).

Inputs required:
- Firm name
- Website URL

The skill researches the firm using publicly available data (website, Google reviews, Facebook, ad presence) and generates 3 specific workflow gaps with cost estimates. Output is a rendered card with a copy-as-email button.

**Quality check before sending:**
- All 3 gaps are supported by actual research, not generic assumptions
- Cover note references something specific and real about the firm
- No gap is repeated across the three
- Every gap has a concrete cost estimate

### Step 3 — Send the outreach email

**Email 1 — the ask (do not attach the snapshot yet):**

> [First name] —
>
> I put together a short workflow snapshot for [Firm Name] based on what I could see externally — three specific gaps, rough cost estimates on each. Want me to send it over?
>
> John-Carlos Saponara
> Blue Tusk LLC

Subject line options (pick based on what was most specific in the research):
- "what I found looking at [Firm Name]'s intake flow"
- "short external look at [Firm Name]"
- "[Firm Name] — three things I noticed"

**Do not automate this send.** Each email is sent manually. The snapshot is personalized — the outreach email must feel the same way.

### Step 4 — If they reply yes, send the snapshot

Copy the snapshot plain text from the card widget and paste it into a reply. No additional pitch. No price mention. Just the snapshot.

Close with:

> This is based on what's publicly visible — a 30-minute call with your internal intake and case flow data would let me give you specific numbers on what each of these is actually costing the firm. Happy to do that if it would be useful.

### Step 5 — If no reply, one follow-up only

Send 5–7 days after the first email:

> Still happy to send it over if useful — just say the word.

One follow-up maximum. Do not continue the sequence after that. Move on.

### Step 6 — If they book a call

Follow the discovery call SOP: [[business/sales/2026-03-30-audit-call-flow]] *(update this file when the call flow is revised to reflect snapshot-first positioning).*

---

## What to Track

For each batch of 10–15 outreaches, record:

- Firm name and URL
- Date sent
- Response: yes / no reply / polite decline
- If yes: did they book a call?
- If they booked: did it convert to a paid engagement?

This data will determine whether and how to scale. If response rate on the snapshot approach is meaningfully above the previous method (target: 2+ replies per 10 sends), the next step is increasing batch size and building out the scale infrastructure.

---

## What Is Not In Scope for This SOP

- LinkedIn outreach (currently paused — low signal-to-noise for PI attorneys)
- Instantly automated sequences (paused — superseded by this method)
- Paid advertising (not in current budget)
- Post-call follow-up and retainer conversion (covered separately in sales SOPs)

---

## Next Review

Review this SOP after the first 3 batches (30–45 outreaches) or when a meaningful pattern emerges in the response data — whichever comes first. If response rate is strong, update this file with scale infrastructure. If response rate is still low, return to the pipeline diagnosis document and run another adversarial pass.
