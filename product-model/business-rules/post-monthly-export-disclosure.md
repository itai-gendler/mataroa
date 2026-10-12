---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::blog-settings"
        }
      ]
    }
  ],
  "permits": [
    {
      "unattended": true,
      "when": [
        {
          "entity": "blog",
          "fact": "Mail export enabled",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/management/commands/mailexports.py"
    }
  ]
}
---

# Post disclosure is limited to enabled unattended export processing

Post disclosure is limited to enabled unattended export processing.
