---
title: "Notion Sandbox — Database and Page IDs"
date: 2026-10-08
tags: [project, tool, ai]
ai: claude
status: ok
---

# Notion Sandbox: Database and Page IDs

## Summary
IDs for every database and hub page in JC's Notion sandbox ("Operating System (Sandbox)"), built from [[20261008_notion-build-spec-sandbox]] v1 on 2026-10-08. Use these for the sandbox's System Registry and for testing skills against the sandbox. **Sandbox only:** the real build will get new IDs.

## Context
- Reported by Notion AI after the build. Data source IDs are taken from the `/ds/` links it returned (the second ID in each link).
- Top-level pages: Operating System (Sandbox) `8ab9250c1af145c1ad1342caad9d1065`; Operating System (Restricted) `c3196b17b0a34e45bec186e4c506cafe` (private to JC; holds Contracts and Invoices).

## Content

### Databases

| Database | Database ID | Data source ID | Area |
|---|---|---|---|
| Companies | `dbe82702d16741a9aca894aa99ac24e6` | `749074dd9d7d40098b47841bb80d51fc` | Sandbox |
| People | `e40dadf339b04c59bfadcce37d5021a9` | `3fe77049c03d4160a0eac46ae6639917` | Sandbox |
| Projects | `71c9691c40414ab5917a70802b1ee391` | `0ac1daaa95d241dc8aef44b1df153a21` | Sandbox |
| Tasks | `7a314be4d7b9416da6b7b22e87c29b1d` | `5c9d16fa572b469d9aa179dfdf92e171` | Sandbox |
| Knowledge | `77ded74bb91b466cbe89e44e5c026f22` | `ea98a02b12bc40c48594c9c32258464c` | Sandbox |
| AI Drafts | `b1b6c6782db44b148a2470f71ea43d6f` | `d8ce42ea1a584bfeb65ad01037c59942` | Sandbox |
| Meeting Notes | `7dffada13ed24a3fac29a261cc4fc826` | `5edf424f210a40e49a02e83011254981` | Sandbox |
| Handoffs | `a177dcf3cd274ba69d5352e285a7f74f` | `ce596e39248c452cad3bd8d99b4461ac` | Sandbox |
| Documents | `a61eb6bd4742428f9191140e7ca6271e` | `ca0e33e921674f09a2346c4a04929809` | Sandbox |
| Contracts | `7d580f3994a64e3e99aa096c357c2326` | `28a709716b864c7e846ce93f3759f07b` | Restricted |
| Invoices | `d02a2db0a108436b9a0bd233f659b57a` | `f9d24da2bf714bf6865e112333b9d877` | Restricted |

### Pages

| Page | ID |
|---|---|
| Home | `0832630309c043998306834b17ea387d` |
| Clients | `2cba250596274da1a4382c3909e06603` |
| All work | `7258da9db85546718642fe3327104440` |
| My page (template) | `7c8692bd0efb48508873eff6caa91a91` |
| System Registry | `41a65693f0364e00b97884a521a71884` |
| Registry: Projects | `be0c8005606a4fe292c078b3729eff43` |
| How to use this system | `5ccbbabd82ae4e0293651f2ccb5babc5` |
| Getting started | `5f005217e643460f9a2e3b3b4c910110` |

## Next steps
- [ ] Copy the database table into the sandbox System Registry (Database index).
- [ ] Point the scratch `catch-up` skill at the sandbox AI Drafts data source when testing.
- [ ] Delete the older scratch databases ("SCRATCH - AI Drafts Test", "SCRATCH - Skills Test") once skills are tested against the sandbox.
