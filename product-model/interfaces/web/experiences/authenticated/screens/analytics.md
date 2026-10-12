---
{
  "entities": [
    {
      "entity": "post",
      "shows": [
        "Title",
        "Slug",
        "Proper link"
      ]
    },
    {
      "entity": "post-views",
      "shows": [
        "Daily counts",
        "Total views"
      ]
    },
    {
      "entity": "page-views",
      "shows": [
        "Path",
        "Daily counts",
        "Total views"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py"
    }
  ]
}
---

# Analytics

Owned writing and Blog-path request-count reports, with daily buckets and totals.
