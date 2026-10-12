---
{
  "kind": "primary",
  "routes": {
    "r-users": "R USERS"
  },
  "steps": [
    {
      "text": "The administrator selects the report, filter or reporting date.",
      "kind": "actor",
      "entities": [],
      "actor": "administrator",
      "contexts": {
        "r-users": {
          "place": "web::restricted::users"
        }
      }
    },
    {
      "text": "Custom account collections, eligibility/approval filters and posting/image/storage rankings are presented with actual pagination.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Email",
            "Joined date",
            "Premium",
            "Approved",
            "Delisted",
            "Processor customer",
            "Post count",
            "Image count",
            "Storage used"
          ]
        },
        {
          "entity": "image",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "r-users": {
          "place": "web::restricted::users"
        }
      },
      "actor": "administrator"
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

# Account collections and rankings

## Trigger

Account collections and rankings: Read moderation.

## Outcome

Custom account collections, eligibility/approval filters and posting/image/storage rankings are presented with actual pagination.
