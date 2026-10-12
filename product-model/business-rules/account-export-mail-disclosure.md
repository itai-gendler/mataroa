---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::blog-settings"
        }
      ],
      "facts": [
        "Email",
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
          "fact": "Mail export enabled",
          "is": true
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has",
          "entity": "author"
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

# Account disclosure is limited to enabled unattended export processing

Account disclosure is limited to enabled unattended export processing.
