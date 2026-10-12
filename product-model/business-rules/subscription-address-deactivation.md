---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-subscription",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::public::email-subscription"
        },
        {
          "place": "web::authenticated::email-subscription"
        }
      ],
      "facts": [
        "Active"
      ],
      "to": "Inactive"
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

# Email subscription modification is limited to Reader or Author

Email subscription modification is limited to Reader or Author.
