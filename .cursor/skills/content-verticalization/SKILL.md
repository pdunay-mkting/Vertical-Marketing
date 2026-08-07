---
name: content-verticalization
description: >-
  Content Verticalization — Sales Assistant playbook that takes a top-performing
  horizontal collateral asset (via MINE + Content Center), applies lexicon swaps
  for a target vertical, runs Content Toolbox + portfolio review, gets Customer
  Reference and Legal approvals, then publishes in AEM. Use when Paul asks to
  verticalize content, industry-adapt collateral, or run the content
  verticalization mega-prompt.
---

# Content Verticalization

## Where it runs

| Role | System |
|------|--------|
| Runtime | **Sales Assistant** |
| Source of truth | This Cursor skill folder |

## Paste into Sales Assistant

Open [sales-assistant-mega-prompt.md](sales-assistant-mega-prompt.md) and paste the fenced playbook block into Sales Assistant as the playbook / system prompt.

## Flow (high level)

1. Product → MINE top horizontal collateral → pick Source Offer ID
2. Resolve PDF URL in Content Center → extract source text
3. Pick vertical → approve lexicon swaps → apply light phrasing only
4. Optional customer-reference callout
5. New Offer ID (Mo-Hub) + title
6. Content Toolbox style guide → portfolio content review
7. Customer Reference approval (Michael Johnson) → Legal (Jeff Picozzi)
8. AEM publish → return published URL

Depth = lexicon swaps + light phrasing. Not a deep rewrite.

## Checklist

```
Content Verticalization — [product] → [vertical]
[ ] Source Offer ID chosen (MINE)
[ ] PDF URL resolved (Content Center)
[ ] Source text in hand (PDF → text)
[ ] Lexicon swaps approved + applied
[ ] Optional customer-reference callout (skipped or approved)
[ ] New Offer ID from Mo-Hub
[ ] Title chosen
[ ] Content Toolbox style guide (+ confirmation number)
[ ] Portfolio content review → final piece
[ ] Customer Reference approval (Michael Johnson)
[ ] Legal approval (Jeff Picozzi)
[ ] AEM published URL returned
```

## Guardrails

- Never invent Offer IDs, PDF URLs, customer references, Slack approvals, or AEM URLs
- Never send Slack or publish without the named approver’s confirmation
- Stop at every human gate
