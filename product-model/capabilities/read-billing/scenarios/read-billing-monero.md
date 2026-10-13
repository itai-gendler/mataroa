---
{
  "kind": "primary",
  "routes": {
    "w-billing": "W BILLING"
  },
  "steps": [
    {
      "text": "The author opens the billing overview.",
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
      "text": "Billing presents the current plan, the 0.05 XMR yearly price and the Monero address; a Free account is asked to send 0.05 XMR and allow one hour for verification. No processor subscription or payment history is shown.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Premium",
            "Grandfathered",
            "Monero address"
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
      "target": "main/views/billing.py#billing_overview"
    }
  ]
}
---

# Monero

## Trigger

An author with a Monero address opens Billing.

## Outcome

Billing presents the Monero payment form: plan, 0.05 XMR yearly price and address. Verification and activation are not established.
