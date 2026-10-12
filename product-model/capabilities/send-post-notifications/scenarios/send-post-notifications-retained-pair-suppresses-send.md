---
{
  "kind": "edge",
  "routes": {
    "w-newsletter": "W NEWSLETTER"
  },
  "steps": [
    {
      "text": "The scheduled real processing run starts.",
      "kind": "condition",
      "entities": [],
      "unattended": true,
      "contexts": {
        "w-newsletter": {
          "place": "web::authenticated::newsletter"
        }
      }
    },
    {
      "text": "A retained unique pair suppresses another send attempt; delivery is not inferred from that accounting.",
      "kind": "condition",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Newsletter eligibility"
          ]
        },
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
        "w-newsletter": {
          "place": "web::authenticated::newsletter"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/management/commands/processnotifications.py#Command.handle"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/management/commands/processnotifications.py#get_email"
    }
  ]
}
---

# Retained pair suppresses send

## Trigger

Retained pair suppresses send: Send post notifications.

## Outcome

A retained unique pair suppresses another send attempt; delivery is not inferred from that accounting.
