---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author begins external payment-method setup and follows confirmation.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::new-card"
        }
      },
      "capability": "add-card"
    },
    {
      "text": "Processor setup and successful confirmation attach the selected external payment method; confirmation reports completion.",
      "kind": "product",
      "entities": [
        {
          "entity": "card",
          "effect": "creates",
          "facts": [
            "Processor identity",
            "Customer association",
            "Brand",
            "Last digits",
            "Expiry",
            "Default"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::new-card"
        }
      },
      "actor": "author",
      "capability": "add-card"
    },
    {
      "text": "The completed payment-method operation redirects the author to Billing.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "add-card",
      "contexts": {
        "web": {
          "place": "web::authenticated::new-card"
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
      "target": "main/views/billing.py#BillingCard"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_card_confirm"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_overview"
    }
  ]
}
---

# Added

## Trigger

Complete card work and inspect Billing.

## Outcome

Processor setup and successful confirmation attach the selected external payment method; confirmation reports completion. For an existing external customer, Billing presents subscription status, cards and invoice projections; paid period dates are shown only when the latest invoice is paid.
