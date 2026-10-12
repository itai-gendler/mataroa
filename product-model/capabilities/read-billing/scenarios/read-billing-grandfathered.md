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
      "text": "The grandfathered branch presents that entitlement without the ordinary processor overview.",
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

# Grandfathered

## Trigger

Grandfathered: Read billing.

## Outcome

The grandfathered branch presents that entitlement without the ordinary processor overview.
