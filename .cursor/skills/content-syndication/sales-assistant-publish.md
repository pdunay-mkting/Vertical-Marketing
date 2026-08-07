# Sales Assistant publish notes

Content Syndication is designed for **both** Cursor and **Sales Assistant**.

## Source of truth

| Artifact | Location |
|----------|----------|
| Orchestrator | `.cursor/skills/content-syndication/SKILL.md` |
| Step skills | `.cursor/skills/content-syndication-*/SKILL.md` |
| This file | Dual-publish checklist |

When procedure changes, update Cursor skills first, then refresh the SA prompt.

## What Sales Assistant should own natively

- SGID → accounts  
- Open product pipeline sums  
- Qualify / disqualify (≥ 50% of potential)  
- Export: Account ID, name, country, domain URL  

Prefer calling existing Sales Assistant Salesforce capabilities rather than re-implementing in Cursor-only tools.

## What to paste into Sales Assistant (orchestrator prompt)

Collapse the Cursor orchestrator + step skills into one SA playbook that:

1. Asks product (Ansible / RHEL / OpenShift → AI / Virtualization / core)
2. Points at PAI Tableau (live) + spreadsheet backup + potential field / $1M default
3. Runs pipeline qualify via SA
4. Instructs MINE query + VPN reminder; waits for Offer ID(s)
5. Instructs content.redhat.com PDF resolve steps
6. Drafts agency email (verbatim substance from `content-syndication-agency-email`)
7. Walks SOW → ServiceNow → Google Form → PO email to agency (AR@redhat.com)
8. Monthly KPI snapshot or first-Monday reminder
9. Nurture: ask yes/no → hand off if yes

## Gaps to call out in SA

Human-assisted unless SA gains connectors:

- Tableau live extract  
- MINE (VPN)  
- content.redhat.com PDF hunt  
- ServiceNow catalog + Google Form fill  
- Email send / inbox watch  

SA can still **guide** those steps even without automation.

## Publish checklist

- [x] Cursor skills reviewed via dry run (OpenShift core)  
- [x] SA mega-prompt drafted — see [sales-assistant-mega-prompt.md](sales-assistant-mega-prompt.md)  
- [ ] Product potential field names confirmed for Ansible, RHEL, OpenShift AI, OpenShift Virtualization  
- [x] Agency email To left blank in SA template  
- [x] Nurture explicitly out of scope / handoff only  
- [ ] Pasted into Sales Assistant and smoke-tested 
