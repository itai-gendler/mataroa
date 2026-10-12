---
{
  "kind": "primary",
  "routes": {
    "s": "S"
  },
  "steps": [
    {
      "text": "The caller submits a customer-owned default selection or an attachment event.",
      "kind": "actor",
      "entities": [],
      "actor": "stripe",
      "contexts": {
        "s": {
          "place": "stripe-webhook"
        }
      }
    },
    {
      "text": "An attachment event sets a default only when the external customer has none.",
      "kind": "product",
      "entities": [
        {
          "entity": "card",
          "effect": "changes",
          "facts": [
            "Default"
          ]
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
      "target": "main/views/billing.py#billing_card_default"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_stripe_webhook"
    }
  ]
}
---

# Attached without default

## Trigger

Attached without default: Make card default.

## Outcome

An attachment event sets a default only when the external customer has none.
