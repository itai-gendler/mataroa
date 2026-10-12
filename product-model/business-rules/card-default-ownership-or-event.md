---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "card",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::billing"
        },
        {
          "place": "web::authenticated::subscribe-premium"
        },
        {
          "place": "stripe-webhook"
        }
      ],
      "facts": [
        "Default"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has",
          "entity": "account"
        },
        {
          "verb": "has",
          "entity": "author"
        }
      ]
    },
    {
      "actors": [
        "stripe"
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

# Card modification is limited to its owner or Stripe

Card modification is limited to its owner or Stripe.
