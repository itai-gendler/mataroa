---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-subscription",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::subscribers"
        }
      ],
      "facts": [
        "Email",
        "Active"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has",
          "entity": "blog"
        },
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
      "target": "main/views/general.py"
    }
  ]
}
---

# Email subscription disclosure is limited to its owner

Email subscription disclosure is limited to its owner.
