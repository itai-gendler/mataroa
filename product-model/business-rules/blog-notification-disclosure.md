---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "blog",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::newsletter"
        }
      ]
    }
  ],
  "permits": [
    {
      "unattended": true,
      "when": [
        {
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

# Blog disclosure is limited to enabled unattended notification processing

Blog disclosure is limited to enabled unattended notification processing.
