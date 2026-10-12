---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Username",
        "Premium",
        "Grandfathered"
      ]
    },
    {
      "entity": "blog",
      "shows": [
        "Title",
        "Comments enabled",
        "Newsletter enabled",
        "Automatic backups enabled"
      ]
    },
    {
      "entity": "comment",
      "shows": [
        "Approval"
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

# Dashboard

Current writing identity, pending-response count and feature preferences.
