---
{
  "kind": "primary",
  "routes": {
    "w-subscribers": "W SUBSCRIBERS"
  },
  "steps": [
    {
      "text": "The author opens the active recipient collection.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-subscribers": {
          "place": "web::authenticated::subscribers"
        }
      }
    },
    {
      "text": "Current active owned enrollment addresses are presented.",
      "kind": "product",
      "entities": [
        {
          "entity": "email-subscription",
          "effect": "reads",
          "facts": [
            "Email",
            "Active"
          ]
        }
      ],
      "contexts": {
        "w-subscribers": {
          "place": "web::authenticated::subscribers"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#NotificationList"
    }
  ]
}
---

# Active owned addresses

## Trigger

Active owned addresses: Read subscribers.

## Outcome

Current active owned enrollment addresses are presented.
