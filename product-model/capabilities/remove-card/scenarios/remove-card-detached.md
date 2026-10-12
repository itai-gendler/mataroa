---
{
  "kind": "primary",
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
      "text": "The customer-owned external method is detached and Billing is reached, even when the presentation hid removal of a Premium default card.",
      "kind": "product",
      "entities": [
        {
          "entity": "card",
          "effect": "removes"
        }
      ],
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

# Detached

## Trigger

Detached: Remove card.

## Outcome

The customer-owned external method is detached and Billing is reached, even when the presentation hid removal of a Premium default card.
