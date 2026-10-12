---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Username",
        "Email",
        "Joined date",
        "Premium",
        "Grandfathered",
        "Approved",
        "Processor customer",
        "Post count",
        "Image count",
        "Storage used"
      ]
    },
    {
      "entity": "image",
      "shows": [
        "Size"
      ]
    },
    {
      "entity": "post",
      "shows": [
        "Title",
        "Publication date",
        "Proper link",
        "Created time"
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

# Users

Custom users report with the traced aggregate, collection or date-specific projections.
