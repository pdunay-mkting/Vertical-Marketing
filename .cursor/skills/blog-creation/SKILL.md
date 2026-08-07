---
name: blog-creation
description: >-
  Orchestrates Red Hat blog creation end-to-end: idea, persona(s), industry,
  RAG research brief, product-fit suggest + approve, blog draft with Red Hat
  blog-writer standards, draft approve, downloadable Markdown of the final post,
  then optional high-priority and strategic account share lists. Use when the
  user wants a blog post workflow, blog creation playbook, or Sales Assistant
  mega-prompt for writing blogs.
---

# Blog creation

Walk a marketer from idea to a publication-ready Red Hat blog draft. Run steps
**in order**. Stop at every human gate. Never invent customer names, metrics,
or product claims not supported by the approved brief / product fit.

## Dual publish

| Artifact | Location |
|----------|----------|
| This orchestrator | `.cursor/skills/blog-creation/SKILL.md` |
| Sales Assistant mega-prompt | [sales-assistant-mega-prompt.md](sales-assistant-mega-prompt.md) |

Update this skill first; refresh the mega-prompt when procedure changes.

## Checklist

```
Blog creation — [idea short title]
[ ] Idea captured
[ ] Persona(s) selected
[ ] Industry / vertical set (or horizontal)
[ ] RAG research run (idea + persona + industry)
[ ] Research brief approved
[ ] Product / technical fit suggested
[ ] Product fit approved
[ ] Blog draft delivered (blog-writer standards)
[ ] Blog draft approved
[ ] Downloadable Markdown file ready
[ ] Account share list (skipped or delivered)
```

## Steps

### 1 — Idea
Ask: **What's the idea behind this blog?**  
Examples of idea types: regulation, market/AI announcement to comment on, topical area (e.g. AI-assisted drug discovery).

### 2 — Persona(s)
Offer the canonical Red Hat list; allow **one or a few**:
1. C-Suite IT Leader (CIO, CTO, VP of Engineering)
2. AppDev IT Decision Maker (Director of Engineering, VP of Product)
3. Developer
4. SysAdmin / Platform Engineer
5. Architect

### 3 — Industry / vertical
Ask for industry/vertical (or "horizontal" / none) so terminology matches.

### 4 — Topic research (RAG)
Run Sales Assistant **RAG discovery** using **only**:
- idea
- persona(s)
- industry / vertical

Do not add a separate source menu.

### 5 — Research brief (human gate)
Present a short structured brief:
- Key facts
- Tensions
- Business impact
- 3–5 use cases

Wait for explicit **approve** before continuing.

### 6 — Product / technical fit (human gate)
**Suggest** Red Hat product / technical fit from idea + persona + industry + approved brief.  
Do not ask for product first. Wait for explicit **approve** (or edits + approve).

### 7 — Draft blog
After product-fit approve, draft immediately (no extra intake for target blog, journey stage, SEO, author, or CTA).  
Infer target blog from persona when possible (exec → corporate; practitioner/Developer persona → Developer; partner-heavy → Partner Connect) and state the choice in metadata.

Apply **red-hat-blog-writer** standards — see mega-prompt draft section for voice, gotchas, CTAs, SEO, and output template. In Cursor, also load `.agents/skills/red-hat-blog-writer/SKILL.md` when available.

### 8 — Approve blog draft (human gate)
Wait for explicit **approve** of the final blog output (revise on request).

### 8b — Downloadable Markdown
After approve, write a clean `.md` file the marketer can download/save:
- Name: `blog-[short-slug-from-headline].md`
- Body: publishable post only (headline → What's next + metadata); no checklist, research, product-fit, or Review Notes
- In Cursor: write the file to the workspace (e.g. `blog-drafts/`) and give the path
- In Sales Assistant: attach/download if supported; else one fenced block + recommended filename

### 9 — Account share suggestions (optional)
Ask: Would you like me to suggest a list of potential accounts to share this blog post with?

- **No** → mark skipped; done.
- **Yes** → use Sales Assistant / Sales Cloud to return two lists grounded in approved product fit (+ industry when set):
  1. **High-priority accounts** (focused short list)
  2. **Additional strategic targets** (expansion / longer-term short list)
  - Fields: Account ID, name, country, domain URL, one-line why

## Guardrails

- Research and use cases before product fit — do not reverse into a feature pitch.
- Flag unknowns as **[TBD]**; do not invent facts, metrics, customer names, or account records.
- Original content only (no republishing existing internet copy).
