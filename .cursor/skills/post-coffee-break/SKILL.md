---
name: post-coffee-break
description: >-
  Post-Coffee Break — Sales Assistant playbook that turns a completed Coffee
  Break (or short webinar) transcript into top keywords, one notable quote per
  speaker, LinkedIn + X posts, a ~750-word blog summary, then optional relevant
  accounts. Use when Paul asks for post-webinar promo, Coffee Break follow-up
  content, or a post-Coffee Break mega-prompt.
---

# Post-Coffee Break

## Where it runs

| Role | System |
|------|--------|
| Runtime | **Sales Assistant** |
| Source of truth | This Cursor skill folder |

## Paste into Sales Assistant

Open [sales-assistant-mega-prompt.md](sales-assistant-mega-prompt.md) and paste **only** the block between the `~~~~` markers into Sales Assistant as the playbook / system prompt.

## What it produces

1. Top 10 keywords from the transcript
2. One notable quote per speaker (verbatim from transcript)
3. LinkedIn post (1) + X post (1)
4. Blog summary (~750 words, ~650–850 band)
5. After package approve: ask whether to find relevant accounts

## Checklist

```
Post-Coffee Break — [session title]
[ ] Transcript ingested
[ ] Speakers confirmed
[ ] Optional metadata captured (title, date, replay URL)
[ ] Top 10 keywords extracted
[ ] Notable quotes (1 per speaker)
[ ] LinkedIn post drafted (1)
[ ] X post drafted (1)
[ ] Blog summary drafted (~750 words)
[ ] Full package reviewed / approved
[ ] Accounts question asked (yes path completed or skipped)
```

## Guardrails

- Transcript text required — do not claim to transcribe video/audio
- Never invent speakers, quotes, stats, URLs, product claims, or Account IDs
- Must ask the accounts question after package approval before ending
