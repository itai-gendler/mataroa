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
      "text": "An attachment event with an existing default leaves it unchanged.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "s": {
          "place": "stripe-webhook"
        }
      }
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

# Existing default retained

## Trigger

Existing default retained: Make card default.

## Outcome

An attachment event with an existing default leaves it unchanged.
