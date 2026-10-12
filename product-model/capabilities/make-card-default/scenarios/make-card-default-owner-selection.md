---
{
  "kind": "primary",
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
      "text": "The selected customer-owned method becomes the default and Billing is reached.",
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

# Owner selection

## Trigger

Owner selection: Make card default.

## Outcome

The selected customer-owned method becomes the default and Billing is reached.
