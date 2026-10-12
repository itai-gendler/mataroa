---
{
  "kind": "primary",
  "routes": {
    "r-users": "R USERS"
  },
  "steps": [
    {
      "text": "The administrator submits removal of approval for the selected identity.",
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
      "text": "The selected identity’s approval flag becomes false.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Approved"
          ]
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
      "target": "main/views/moderation.py#user_unapprove"
    }
  ]
}
---

# Flag cleared

## Trigger

Flag cleared: Unapprove user.

## Outcome

The selected identity’s approval flag becomes false.
