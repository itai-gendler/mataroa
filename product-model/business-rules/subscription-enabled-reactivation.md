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
      "to": "Active"
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

# Email subscription modification is limited to a public participant while newsletter is enabled

Email subscription modification is limited to a public participant while newsletter is enabled.
