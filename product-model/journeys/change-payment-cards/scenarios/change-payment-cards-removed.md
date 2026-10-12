---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author confirms detachment of the selected external payment method.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::card"
        }
      },
      "capability": "remove-card"
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
        "web": {
          "place": "web::authenticated::card"
        }
      },
      "actor": "author",
      "capability": "remove-card"
    },
    {
      "text": "The completed payment-method operation redirects the author to Billing.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "remove-card",
      "contexts": {
        "web": {
          "place": "web::authenticated::card"
        }
      }
    },
    {
      "text": "The author opens the billing overview.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::billing"
        }
      },
      "capability": "read-billing"
    },
    {
      "text": "For an existing external customer, Billing presents subscription status, cards and invoice projections; paid period dates are shown only when the latest invoice is paid.",
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
        "web": {
          "place": "web::authenticated::billing"
        }
      },
      "actor": "author",
      "capability": "read-billing"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#BillingCardDelete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_overview"
    }
  ]
}
---

# Removed

## Trigger

Complete card work and inspect Billing.

## Outcome

The customer-owned external method is detached and Billing is reached, even when the presentation hid removal of a Premium default card. For an existing external customer, Billing presents subscription status, cards and invoice projections; paid period dates are shown only when the latest invoice is paid.
