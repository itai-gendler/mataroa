---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ],
      "facts": [
        "Email"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "reader",
        "author"
      ]
    },
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
      "target": "main/views/general.py"
    }
  ]
}
---

# Account disclosure is limited to Reader or Author

Account disclosure is limited to Reader or Author.
