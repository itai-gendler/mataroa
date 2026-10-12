---
{
  "entities": [
    {
      "entity": "post",
      "shows": [
        "Title",
        "Publication date",
        "Proper link",
        "Created time"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Username"
      ]
    },
    {
      "entity": "post-views",
      "shows": [
        "Daily counts",
        "Total views"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/moderation.py"
    }
  ]
}
---

# Posts

Custom posts report with the traced aggregate, collection or date-specific projections.
