---
{
  "kind": "validation",
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
      "text": "Invalid owned-card selection is refused without setting a default.",
      "kind": "condition",
      "entities": [
        {
          "entity": "card",
          "effect": "reads",
          "facts": []
        }
      ],
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

# Invalid owned card

## Trigger

Invalid owned card: Make card default.

## Outcome

Invalid owned-card selection is refused without setting a default.
