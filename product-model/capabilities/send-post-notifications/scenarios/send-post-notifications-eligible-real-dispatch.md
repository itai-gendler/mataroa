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
      "text": "A real scheduled run selects yesterday’s eligible writing and current active recipients, records each new pair before SMTP, attempts multipart mail and records completion when no recipient exception was recorded.",
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

# Eligible real dispatch

## Trigger

Eligible real dispatch: Send post notifications.

## Outcome

A real scheduled run selects yesterday’s eligible writing and current active recipients, records each new pair before SMTP, attempts multipart mail and records completion when no recipient exception was recorded.
