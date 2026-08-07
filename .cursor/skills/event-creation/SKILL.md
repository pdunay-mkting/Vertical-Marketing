---
name: event-creation
description: >-
  Orchestrates Red Hat event creation end-to-end for roundtables, webinars, or
  similar: format, topic, speakers, persona(s), industry, country, commercial
  segment, then a ticket/email-ready segment pull request (approve), abstract approve,
  asset pack, a single deliverables doc, then optional invite account list.
  Use when the user wants an event, roundtable, webinar, or Sales Assistant
  mega-prompt for event creation.
---

# Event creation

Walk any marketer (PMM, field, vertical, ABM, partner, etc.) from topic to a
full event package for a roundtable, webinar, or similar. Ask the **7 intake
questions one at a time** and wait for a reply before the next — do not stack
questions. After intake, deliver a **ticket/email-ready segment pull request**,
then the abstract. Hard human gates before the asset pack: **segment pull
request approve**, then **abstract approve**. After assets, write one
**deliverables doc**, then ask about an
invite account list. Never invent speakers, customer names, metrics, or dates.

## Dual publish

| Artifact | Location |
|----------|----------|
| This orchestrator | `.cursor/skills/event-creation/SKILL.md` |
| Sales Assistant mega-prompt | [sales-assistant-mega-prompt.md](sales-assistant-mega-prompt.md) |

Update this skill first; refresh the mega-prompt when procedure changes.

## Checklist

```
Event creation — [short title]
[ ] Format captured
[ ] Topic captured
[ ] Speakers captured (name, title, company; look up missing titles)
[ ] Persona(s) selected
[ ] Industry / vertical set
[ ] Country set
[ ] Commercial segment set
[ ] Segment pull request delivered
[ ] Segment pull request approved
[ ] Abstract drafted (~250 words; 150–300)
[ ] Abstract approved
[ ] Agenda drafted
[ ] Invite email drafted
[ ] Landing page copy drafted
[ ] Follow-up emails drafted (attended + regrets)
[ ] High-priority / strategic target brainstorm
[ ] Asset pack approved
[ ] Deliverables doc created
[ ] Invite account list (skipped or delivered)
```

## Steps

### 1 — Intake (7 questions, one at a time)
Ask **exactly one** question per turn. Wait for the marketer's reply before
asking the next. Do not combine questions, preview later steps, or dump a
multi-field form. Keep each turn short.

Order:

1. **Format** — roundtable, webinar, or other event type
2. **Topic** — what the event is about
3. **Speakers** — only names (and title / company) the marketer provides.
   Look up a missing title if needed. Do **not** invent or suggest speakers.
4. **Persona(s)** — same canonical Red Hat list as blog creation; one or a few:
   1. C-Suite IT Leader (CIO, CTO, VP of Engineering)
   2. AppDev IT Decision Maker (Director of Engineering, VP of Product)
   3. Developer
   4. SysAdmin / Platform Engineer
   5. Architect
5. **Industry / vertical**
6. **Country**
7. **Commercial segment** — Enterprise, Commercial, or Both

After question 7 is answered, go to Step 2 (do not draft the abstract yet).

### 2 — Segment pull request
Immediately after intake, deliver a **copy-paste ready** segment description the
marketer can email to their team or paste into a ticket.

Include:
- Event format + short topic (context for the pull)
- Audience = **all marketable contacts** matching:
  - Industry / vertical
  - Persona(s)
  - Country
  - Commercial segment
- Optional filters only if the marketer already gave them
- Note that list size differs by format; criteria shape does not

Do **not** invent filters, list counts, or system-specific query syntax unless
the marketer supplied it. Wait for explicit **approve** (or edits + approve)
before the abstract.

### 3 — Abstract (human gate)
Draft **150–300 words** (target **~250**). Same length and tone for roundtable
and webinar. Cover problem / why now, what attendees get, and who it's for.
Wait for explicit **approve** (or edits + approve) before the asset pack.

### 4 — Asset pack (one pass after abstract approve)
Deliver all of the following in one turn when possible:

1. **Agenda** — attendee-facing timed topics (no separate run-of-show).
2. **Invite email** — short; include date/time, speakers, register CTA,
   abstract snippet. Use `[TBD]` for unknown date/time or URL.
3. **Landing page copy** — headline, subhead, abstract, speaker bios, agenda,
   who should attend, CTA.
4. **Follow-up emails** — (a) attended / thank-you, (b) regrets / no-show.
   Leave placeholders for replay, slides, and CTA for more info.
5. **High-priority / strategic target brainstorm** — loose suggestions for
   accounts or strategic targets that fit the event. Not a formal approve gate;
   do not invent Account IDs or claim CRM lookups you did not run.

Then **STOP**. Ask the marketer to reply **approve** for the deliverables
doc (or edits then approve). Do not create the doc or ask the account question
in this turn.

### 5 — Deliverables doc (mandatory, separate turn)
After they **approve** the asset pack, create **one package** they can save as a file.

- **Required every time:** full content in a fenced markdown block labeled
  `EVENT PACKAGE — COPY INTO A DOC` (copy into Google Docs / Word / .md).
- **Also:** write a `.md` file in Cursor (e.g. `event-creation-[short-slug].md`)
  or generate a downloadable file in Sales Assistant when available.

Document sections in order: intake snapshot, abstract, segment criteria,
agenda, email invite, landing page copy, follow-up emails, high-priority /
strategic targets.

Then go to Step 6 in the **same** turn.

### 6 — Invite account list (mandatory to ask)
Ask exactly:

**Would you like a list of potential accounts we should send this invite to?**

Put it in **Instructions for the marketer**. Reply with **approve** to generate
the list. Never skip asking the question.

- **No approve / decline** → mark skipped; done.
- **Approve** → use Sales Assistant / Sales Cloud when available to propose accounts
  grounded in topic, persona(s), industry, country, and commercial segment:
  1. **High-priority accounts** (focused short list)
  2. **Additional strategic targets** (expansion / longer-term short list)
  - Fields when available: Account ID, name, country, domain URL, one-line why
  - Never invent Account IDs, names, or domains

## Guardrails

- Intake: one question per turn; wait for each reply — never stack the 7.
- After Q7: segment pull request before abstract; wait for **approve**.
- Hard approve gates before assets: **segment pull request**, then **abstract**.
- After assets: wait for **approve** → deliverables doc (mandatory) → must ask the
  invite-account question. Incomplete if either is missing.
- Speakers come from the marketer only; look up missing titles; never invent names.
- Flag unknowns as **[TBD]**; do not invent dates, metrics, customers, or Account IDs.
- Invite list size differs by format; that does not change this process.
