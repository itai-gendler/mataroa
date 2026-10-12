---
{
  "kind": "edge",
  "routes": {
    "w-card": "W CARD"
  },
  "steps": [
    {
      "text": "The author confirms detachment of the selected external payment method.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-card": {
          "place": "web::authenticated::card"
        }
      }
    },
    {
      "text": "A caught detachment error reports the processor problem and redirects to Billing without a confirmed removal.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-card": {
          "place": "web::authenticated::card"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#BillingCardDelete"
    }
  ]
}
---

# Processor failed

## Trigger

Processor failed: Remove card.

## Outcome

A caught detachment error reports the processor problem and redirects to Billing without a confirmed removal.
