---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "premium-subscription",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::subscribe-premium"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has current",
          "entity": "account"
        },
        {
          "verb": "has",
          "entity": "author"
        }
      ],
      "when": [
        {
          "entity": "account",
          "fact": "Premium",
          "is": false
        },
        {
          "entity": "account",
          "fact": "Grandfathered",
          "is": false
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

# Premium subscription creation is limited to its non-Premium non-grandfathered owner

Premium subscription creation is limited to its non-Premium non-grandfathered owner.
