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
      "text": "The Monero branch presents the address, 0.05 XMR price and stated one-hour allowance; verification/activation is not established.",
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

Monero: Read billing.

## Outcome

The Monero branch presents the address, 0.05 XMR price and stated one-hour allowance; verification/activation is not established.
