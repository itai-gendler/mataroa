---
{
  "kind": "validation",
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
      "text": "A missing selected identity returns not found without changing approval.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r-users": {
          "place": "web::restricted::users"
        }
      }
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

# Missing target

## Trigger

Missing target: Unapprove user.

## Outcome

A missing selected identity returns not found without changing approval.
