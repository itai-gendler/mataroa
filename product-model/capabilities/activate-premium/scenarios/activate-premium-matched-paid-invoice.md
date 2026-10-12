---
{
  "kind": "primary",
  "routes": {
    "s": "S"
  },
  "steps": [
    {
      "text": "The provider delivers a paid-invoice event.",
      "kind": "actor",
      "entities": [
        {
          "entity": "invoice",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "stripe",
      "contexts": {
        "s": {
          "place": "stripe-webhook"
        }
      }
    },
    {
      "text": "A paid-invoice event with a matched customer enables Premium and Approved; only a newly enabled transition attempts its administrative mail.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Premium",
            "Approved"
          ]
        },
        {
          "entity": "invoice",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "s": {
          "place": "stripe-webhook"
        }
      },
      "actor": "stripe"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_stripe_webhook"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#_enable_premium"
    }
  ]
}
---

# Matched paid invoice

## Trigger

Matched paid invoice: Activate premium.

## Outcome

A paid-invoice event with a matched customer enables Premium and Approved; only a newly enabled transition attempts its administrative mail.
