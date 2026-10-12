---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-subscription",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::public::email-subscription"
        },
        {
          "place": "web::authenticated::email-subscription"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "reader",
        "author"
      ],
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
      "target": "main/views/general.py"
    }
  ]
}
---

# Email subscription creation is limited to a public participant while newsletter is enabled

Email subscription creation is limited to a public participant while newsletter is enabled.
