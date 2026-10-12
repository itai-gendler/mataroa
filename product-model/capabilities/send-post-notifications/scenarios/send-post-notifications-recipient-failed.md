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
      "text": "A recipient exception clears a newly created pair in the normal path, attempts failure mail to the operating team and leaves completion absent; stale local variables can affect cleanup.",
      "kind": "condition",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Markdown content",
            "Rendered content",
            "Publication date",
            "Proper link"
          ]
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": [
            "Title",
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

# Recipient failed

## Trigger

Recipient failed: Send post notifications.

## Outcome

A recipient exception clears a newly created pair in the normal path, attempts failure mail to the operating team and leaves completion absent; stale local variables can affect cleanup.
