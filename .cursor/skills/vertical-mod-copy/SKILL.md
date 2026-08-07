---
name: vertical-mod-copy
description: >-
  Vertical Mod Copy — Sales Assistant playbook that takes a source Offer ID +
  PDF, analyzes the asset, and fills the Vertical Mod Copy Word template
  (program, label, journey stage, audience, asset links, nurture email) for
  paste into Word, plus a Google Doc version. Use when Paul asks for Vertical
  Mod Copy, template fill for vertical collateral, or the Vertical Mod Copy
  mega-prompt.
---

# Vertical Mod Copy

## Where it runs

| Role | System |
|------|--------|
| Runtime | **Sales Assistant** |
| Source of truth | This Cursor skill folder |
| Word template | [Template.docx](Template.docx) |

## Paste into Sales Assistant

Open [sales-assistant-mega-prompt.md](sales-assistant-mega-prompt.md) and paste **only** the block between the `~~~~` markers into Sales Assistant as the playbook / system prompt.

## What it produces

Filled Vertical Mod Copy fields:

| Field | Notes |
|-------|-------|
| Program | Infer when obvious; else ask once |
| Label | Webinar / Analyst Paper / Datasheet / White Paper / Ebook / Blog / Other |
| Buyer's Journey Stage | Discover / Learn / Evaluate |
| Aligns to program | Best guess from content |
| Target Audience | Roles / buying group |
| Offer ID + Asset Name | From intake / PDF |
| Asset links | Resource library + PDF only (never RHCC) |
| E-mail | SUBJECT + full nurture body |

Plus a Google Doc CTA after final approval.

## Checklist

```
Vertical Mod Copy — [asset name or Offer ID]
[ ] Offer ID + PDF in hand
[ ] Asset links captured (or gaps labeled)
[ ] Program confirmed (inferred or asked)
[ ] PDF text extracted
[ ] Full template drafted (all fields + email)
[ ] Marketer reviewed / approved (or edits applied)
[ ] Final package returned
[ ] Google Doc version offered (link)
```

## Guardrails

- Never invent Offer IDs, URLs, customer proof, or metrics
- Asset links: resource library and PDF only — never RHCC
- One review gate on the full package; propose fields with short rationale
- Never invent a Google Doc URL
