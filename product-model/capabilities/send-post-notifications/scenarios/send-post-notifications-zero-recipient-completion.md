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
      "text": "A real eligible run with no active recipients still records broadcast completion.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Markdown content",
            "Rendered content",
            "Publication date",
            "Proper link",
            "Newsletter eligibility"
          ]
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": [
            "Title",
            "Proper address",
            "Newsletter enabled"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username"
          ]
        },
        {
          "entity": "email-subscription",
          "effect": "reads",
          "facts": [
            "Email",
            "Active",
            "Unsubscribe link"
          ]
        }
      ],
      "contexts": {
        "w-newsletter": {
          "place": "web::authenticated::newsletter"
        }
      }
    },
    {
      "text": "After recipient processing finishes without a recorded exception, the broadcast completion time is saved.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Broadcast completion"
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

# Zero recipient completion

## Trigger

Zero recipient completion: Send post notifications.

## Outcome

A real eligible run with no active recipients still records broadcast completion.
