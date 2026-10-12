---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/models.py"
    }
  ],
  "relations": [
    {
      "entity": "comment",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "post-views",
      "verb": "has",
      "cardinality": "one-to-one"
    }
  ]
}
---

# Post

An independently identified Post. Status, eligibility, links, rendering and fingerprint are derived.

## Information kept

- **Title** — Writing title, at most 300 characters.
- **Slug** — Owner-scoped unique permalink identity, at most 300 characters.
- **Markdown content** — Stored writing, which can be absent or empty; cleanup differs by writing path.
- **Excerpt** — Derived first 240 characters of source in delegated collection summaries.
- **Rendered content** — Derived allowlisted Markdown HTML; delegated reader rendering has its narrower contract.
- **Canonical link** — Derived username-host address.
- **Proper link** — Derived custom-domain or canonical address with the configured post path.
- **Created time** — Creation time.
- **Updated time** — Most recent save time.
- **Publication date** — Calendar date, absent for a Draft.
- **Publication status** — Derived: Draft when undated, Scheduled when future, Published when due or past.
- **Discovery eligibility** — Derived: a date is present and due or past.
- **Revision fingerprint** — Derived from slug, title, Markdown content and publication date; null and empty content differ.
- **Broadcast completion** — Absent initially; real eligible processing records a time without recorded recipient exceptions.
- **Newsletter eligibility** — Derived: newsletter enabled, date precisely yesterday and no broadcast completion.
