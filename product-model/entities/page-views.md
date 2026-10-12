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

# Page views

An independently identified Page views. Blog/path log, including index and RSS; not universally attached to a Page.

## Information kept

- **Path** — Requested Blog path, including index or RSS paths without a static-writing instance.
- **Visit times** — Recorded request times for this Blog/path.
- **Daily counts** — Derived counts grouped into the displayed 25 calendar-date buckets.
- **Total views** — Total recorded requests for this Blog/path, rather than unique visitors.
