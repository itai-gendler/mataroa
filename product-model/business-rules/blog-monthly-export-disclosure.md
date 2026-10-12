---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "blog",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::blog-settings"
        }
      ],
      "facts": [
        "Mail export enabled",
        "Title",
        "Export-stop link"
      ]
    }
  ],
  "permits": [
    {
      "unattended": true,
      "when": [
        {
          "fact": "Mail export enabled",
          "is": true
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "account"
        },
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

# Blog disclosure is limited to enabled unattended export processing

Blog disclosure is limited to enabled unattended export processing.
