---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::subscribe-premium"
        }
      ],
      "facts": [
        "Premium",
        "Approved",
        "Current subscription"
      ]
    }
  ],
  "permits": [
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
      "target": "main/views/billing.py"
    }
  ]
}
---

# Account modification is limited to its owner

Account modification is limited to its owner. Successful supplied intent evidence is evaluated separately; the return handler does not compare its customer with this identity.
