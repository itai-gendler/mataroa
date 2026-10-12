---
{
  "kind": "primary",
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
      "text": "Undated, differently dated, already completed or newsletter-disabled writing is not dispatched.",
      "kind": "condition",
      "entities": [],
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

# Ineligible no dispatch

## Trigger

Ineligible no dispatch: Send post notifications.

## Outcome

Undated, differently dated, already completed or newsletter-disabled writing is not dispatched.
