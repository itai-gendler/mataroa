---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/models.py"
    }
  ]
}
---

# Page

An independently identified Page. Hidden affects listing, not direct access.

## Information kept

- **Title** — Saved static-writing title.
- **Slug** — Owner-scoped unique permalink name; reserved route names are refused.
- **Markdown content** — Saved static-writing source; browser and API cleanup differ.
- **Rendered content** — Allowlisted Markdown HTML derived from the saved source.
- **Link** — Canonical username-host permalink for this static writing.
- **Hidden** — Initially false unless explicitly supplied; affects listing, not direct HTML access.
- **Created time** — Creation time.
- **Updated time** — Most recent save time.
