---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::newsletter"
        }
      ],
      "facts": [
        "Username"
      ]
    }
  ],
  "permits": [
    {
      "unattended": true,
      "when": [
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

# Account disclosure is limited to enabled unattended notification processing

Account disclosure is limited to enabled unattended notification processing.
