---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::newsletter"
        }
      ],
      "facts": [
        "Broadcast completion"
      ]
    }
  ],
  "permits": [
    {
      "unattended": true,
      "when": [
        {
          "fact": "Newsletter eligibility",
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

# Post modification is limited to the eligible unattended dispatch

Post modification is limited to the eligible unattended dispatch.
