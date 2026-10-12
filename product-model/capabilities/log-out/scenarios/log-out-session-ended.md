---
{
  "kind": "primary",
  "routes": {
    "w-dashboard": "W DASHBOARD"
  },
  "steps": [
    {
      "text": "The author ends the current session.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-dashboard": {
          "place": "web::authenticated::dashboard"
        }
      }
    },
    {
      "text": "The session ends and the product redirects to its public landing information.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-dashboard": {
          "place": "web::authenticated::dashboard"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#Logout"
    }
  ]
}
---

# Session ended

## Trigger

Session ended: Log out.

## Outcome

The session ends and the product redirects to its public landing information.
