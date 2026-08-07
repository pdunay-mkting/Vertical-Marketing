# Sales Assistant publish notes

Blog creation is designed for **both** Cursor and **Sales Assistant**.

## Source of truth

| Artifact | Location |
|----------|----------|
| Orchestrator | `.cursor/skills/blog-creation/SKILL.md` |
| SA mega-prompt | [sales-assistant-mega-prompt.md](sales-assistant-mega-prompt.md) |
| Editorial depth (Cursor) | `.agents/skills/red-hat-blog-writer/` |

When procedure changes, update Cursor skills first, then refresh the SA mega-prompt.

**Always** after any mega-prompt edit in this chat: paste a **clean copy** of the full SA prompt (content between the `~~~~` markers only) so the marketer can copy/paste without digging in the file.

## What Sales Assistant should own natively

- **RAG discovery** using idea + persona(s) + industry only  
- Interactive approve gates (research brief, product fit, blog draft)  
- Full draft generation with blog-writer rules inlined in the mega-prompt  
- Optional **account share lists** (high-priority + strategic) via Sales Cloud after draft approve  
- **Downloadable Markdown** of the approved post (attach if SA supports it; else copy/save block)  

## Publish checklist

- [x] Cursor orchestrator drafted  
- [x] SA mega-prompt drafted  
- [x] Post-draft approve + downloadable Markdown + optional account share step added  
- [ ] Pasted into Sales Assistant and smoke-tested (idea → approve brief → approve fit → draft → approve → .md → optional accounts)  
