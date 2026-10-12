---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-subscription",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::public::email-subscription"
        },
        {
          "place": "web::authenticated::email-subscription"
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

# Email subscription disclosure is limited to Reader or Author

Email subscription disclosure is limited to Reader or Author.
