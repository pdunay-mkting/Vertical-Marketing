---
name: content-syndication
description: >-
  Orchestrates Content Syndication ad campaigns end-to-end: product selection,
  PAI target accounts, Salesforce pipeline qualify via Sales Assistant, MINE
  top collateral, PDF resolve, agency SOW email, SOW/PO intake, and monthly
  lead monitor. Use when the user says content syndication, syndication
  campaign, PAI syndication, or wants to create or monitor a content
  syndication program for OpenShift, Ansible, or RHEL.
---

# Content Syndication (orchestrator)

Master playbook for creating and monitoring a Content Syndication campaign.
Source of truth for Cursor; also the template for the Sales Assistant publish prompt
(see [sales-assistant-publish.md](sales-assistant-publish.md)).

Run steps **in order**. Stop at every human gate. Load each step skill before executing it.

## Product parameter (required first)

Ask which product:

- **Ansible**
- **RHEL**
- **OpenShift** → if OpenShift, ask: core OpenShift | **OpenShift AI** | **OpenShift Virtualization**

Carry `product` (and OpenShift subtype) through every later step.

## Step sequence

| Step | Skill | Human gate? |
|------|--------|-------------|
| 1 | `content-syndication-pai` | Confirm account cut / threshold |
| 2 | `content-syndication-qualify` | Confirm qualified list |
| 3 | `content-syndication-mine` | Choose MINE top performers **or** brand-new Offer ID + PDF |
| 4 | `content-syndication-pdf` | Confirm PDF URL(s) — **skip** if PDF link(s) already provided |
| 5 | `content-syndication-agency-email` | User supplies budget + To; approve send |
| 6 | `content-syndication-sow-po` | SOW reply, SNOW, form, PO email |
| 7 | `content-syndication-monitor` | Monthly snapshot or reminder |
| Branch | Nurture | Ask only; do **not** run nurture here |

### Nurture branch

At monitor (or when reviewing leads), ask:

> Do you need to nurture these leads?

- **No** → continue Content Syndication monitor  
- **Yes** → hand off to a **separate nurture workflow** (out of scope here)

### Automated (no skill)

Agency drives contacts → **Integrate** ingest → real-time route to **MDR**. Do not rebuild that path.

## Operating rules

1. Prefer **live systems**; use spreadsheet backups only when live fails.
2. Never invent Offer IDs, PDF URLs, Account IDs, or PO numbers.
3. Never send email without explicit approval.
4. Remind VPN before MINE.
5. Dual-publish: keep step skills and this orchestrator aligned with `sales-assistant-publish.md`.

## Progress checklist (show the user)

```
Content Syndication — [product]
[ ] PAI high-potential accounts
[ ] Pipeline qualify (Sales Assistant / Sales Cloud)
[ ] Agency account list (ID, name, country, domain URL)
[ ] Collateral chosen (MINE or brand-new Offer ID + PDF)
[ ] PDF URL(s) resolved (skip if already provided)
[ ] Agency SOW email drafted / sent
[ ] Agency SOW reply received
[ ] ServiceNow ticket submitted
[ ] Google Form submitted
[ ] PO emailed to agency
[ ] Monthly monitor scheduled
```
