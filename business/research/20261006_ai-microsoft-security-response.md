---
title: "Reusable Response: Connecting Claude to Microsoft 365 (Security Concerns)"
date: 2026-10-06
tags: [research, strategy, client, ai]
ai: claude
status: ok
---

## Summary
A sent client response addressing security concerns about connecting Claude to Microsoft 365 (data leaving the Microsoft boundary, prompt injection, vendor track record). Saved as a reusable and adaptable template for future clients with the same objection. Internal use only.

## Context
- **Client:** Maycomb Capital. See [[xx_Maycomb_AI_Automation_Roadmap_INTERNAL]] for the broader engagement.
- **Trigger:** Varenkha Giordani (Operations Analyst / Office Manager) asked Barry Porozni whether she could connect her Claude account to Microsoft to organize email, meetings, and projects (thread dated 2026-09-28).
- **Barry's two risks:** (1) data leaves the Microsoft boundary and is managed by Anthropic; (2) Claude could act on malicious content in emails or documents as if it were a prompt.
- **Policy status:** Maycomb has no official AI policy on this yet.
- **Martina Sebring (Fractional COO) asked:** is this a quick "phone a friend" or does it need a conversation and scope of work? Broader AI work was deferred until after Affinity.
- **Outcome:** answered as a phone-a-friend. Larger asks (e.g., a governance document) would be a scoped engagement.

## Content

### Sent response (to Martina)

> Hey Martina,
>
> I responded to Barry about this yesterday. There's always a risk. Anthropic's commercial plans (like the team plan Maycomb has) don't train on your data, and the company holds core security certifications like SOC 2 Type II and ISO 27001, so if you're comfortable with Microsoft's standards, nothing here should alarm you on paper. I understand the concern about a much shorter track record. That's a risk acceptance each organization has to make, and I think those who make it - alongside a strong AI strategy - will be more successful in the long run. It's the same call companies faced moving email and documents to the cloud: it felt like a leap at the time, and the early movers built a real advantage.
>
> With regards to prompt injection - the Claude models today are much more resistant than previous models. The prompt injection benchmarks show a <5% success rate for prompt injection attacks. So Varenkha would have to shove 20+ malicious emails into her workflow for it to become a problem (I know that's not how statistics works, but the broader point stands). Even then, any significant action would usually trigger a "Are you sure you want to do this?" from Claude.
>
> This seems reasonable to me as phone a friend. I'm happy to be able to extend your capabilities with your own clients to an extent. If they were to want advice on creating a specific governance document or something like that - it would make more sense for me to get involved directly.

### Reusable argument structure
1. **Acknowledge risk is real.** "There's always a risk."
2. **Data/training:** commercial plans don't train on customer data.
3. **Certifications:** SOC 2 Type II and ISO 27001, framed relative to Microsoft's standards ("if you're comfortable with Microsoft, nothing here should alarm you on paper").
4. **Track record concern:** concede it, frame as an organizational risk acceptance, tie to having a strong AI strategy.
5. **Analogy:** on-prem to cloud (email and documents). Replaced an earlier IBM-to-Microsoft analogy, which was weak: they weren't direct competitors, it wasn't a data-trust story, and it dates the point.
6. **Prompt injection:** newer models are much more resistant; significant actions trigger confirmation prompts.
7. **Scope boundary:** quick advice is free; governance documents or policy work means a direct engagement.

## Next steps
Before reusing, tighten or verify:
- [ ] **Prompt injection figure:** the "<5%" claim and the "20+ emails" illustration are loose (JC flagged the statistics caveat himself). Find the current benchmark source and cite it, or soften to "substantially more resistant than earlier models."
- [ ] **Certifications:** confirm SOC 2 Type II and ISO 27001 against Anthropic's Trust Center before sending to a new client.
- [ ] **Training/data claim:** confirm current commercial terms wording (default no-training on commercial plans vs. a toggle).
- [ ] **Gap:** Barry's first risk (data leaving the Microsoft boundary and being managed by Anthropic) is only addressed indirectly. For future versions, consider a sentence on connector permissions scoping, admin controls, and what data is retained.
- [ ] **Possible follow-on offer:** a short, focused AI usage / governance policy project for Maycomb (Barry floated a smaller project like this).
