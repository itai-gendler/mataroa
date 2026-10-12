---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-subscription",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::newsletter"
        }
      ],
      "facts": [
        "Email",
        "Unsubscribe link"
      ]
    }
  ],
  "permits": [
    {
      "unattended": true,
      "when": [
        {
          "fact": "Active",
          "is": true
        },
        {
          "entity": "blog",
          "fact": "Newsletter enabled",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/management/commands/processnotifications.py"
    }
  ]
}
---

# Email subscription disclosure is limited to the eligible unattended dispatch

Email subscription disclosure is limited to the eligible unattended dispatch.
