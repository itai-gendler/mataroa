---
{
  "kind": "validation",
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
      "text": "Invalid customer or owned-card lookup redirects without detachment.",
      "kind": "condition",
      "entities": [
        {
          "entity": "card",
          "effect": "reads",
          "facts": []
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

# Customer or owned card invalid

## Trigger

Customer or owned card invalid: Remove card.

## Outcome

Invalid customer or owned-card lookup redirects without detachment.
