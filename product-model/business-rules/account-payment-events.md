---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "contexts": [
        {
          "place": "stripe-webhook"
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

# Account modification is limited to Stripe

Account modification is limited to Stripe.
