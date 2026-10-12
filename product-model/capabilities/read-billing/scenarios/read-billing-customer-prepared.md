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
      "text": "The newly created external customer identity is saved on the Account before retrieving the overview.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Processor customer"
          ]
        }
      ],
      "contexts": {
        "w-billing": {
          "place": "web::authenticated::billing"
        }
      },
      "actor": "author"
    },
    {
      "text": "Billing presents the resulting external customer overview; period dates require a paid latest invoice.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Email",
            "Premium",
            "Grandfathered",
            "Processor customer",
            "Current subscription",
            "Monero address"
          ]
        },
        {
          "entity": "premium-subscription",
          "effect": "reads",
          "facts": [
            "Processor identity",
            "Status",
            "Paid-period start",
            "Paid-period end",
            "Cancellation scheduled"
          ]
        },
        {
          "entity": "card",
          "effect": "reads",
          "facts": [
            "Processor identity",
            "Customer association",
            "Brand",
            "Last digits",
            "Expiry",
            "Default"
          ]
        },
        {
          "entity": "invoice",
          "effect": "reads",
          "facts": [
            "Processor identity",
            "Created time",
            "Period start",
            "Period end",
            "Hosted link",
            "PDF link"
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

# Customer prepared

## Trigger

A non-grandfathered author without a Monero address opens Billing without a processor customer, and preparation succeeds.

## Outcome

The newly created processor customer remains associated with the Account and Billing presents the resulting overview.
