---
{
  "kind": "edge",
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
      "text": "An attachment-event defaulting error is logged and acknowledged (200) without confirming a new default.",
      "kind": "condition",
      "entities": [],
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

# Processor failed

## Trigger

Processor failed: Make card default.

## Outcome

An attachment-event defaulting error is logged and acknowledged (200) without confirming a new default.
