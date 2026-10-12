---
{
  "kind": "edge",
  "routes": {
    "w-billing": "W BILLING"
  },
  "steps": [
    {
      "text": "The caller submits a customer-owned default selection or an attachment event.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-billing": {
          "place": "web::authenticated::billing"
        }
      }
    },
    {
      "text": "A caught default-selection error returns service failure (503) without confirming a new default.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-billing": {
          "place": "web::authenticated::billing"
        }
      },
      "actor": "author"
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

# Processor failed

## Trigger

Processor failed: Make card default.

## Outcome

A caught default-selection error returns service failure (503) without confirming a new default.
