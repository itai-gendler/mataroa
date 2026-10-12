---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author requests clearing a scheduled cancellation.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::premium-subscription"
        }
      },
      "capability": "resume-premium"
    },
    {
      "text": "A remotely scheduled cancellation is cleared and Billing is reached.",
      "kind": "product",
      "entities": [
        {
          "entity": "premium-subscription",
          "effect": "changes",
          "facts": [
            "Cancellation scheduled"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::premium-subscription"
        }
      },
      "actor": "author",
      "capability": "resume-premium"
    },
    {
      "text": "The completed subscription operation redirects the author to Billing.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "resume-premium",
      "contexts": {
        "web": {
          "place": "web::authenticated::premium-subscription"
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
      "target": "main/views/billing.py#BillingResume"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_overview"
    }
  ]
}
---

# Resume

## Trigger

Complete subscription work and inspect Billing.

## Outcome

A remotely scheduled cancellation is cleared and Billing is reached. For an existing external customer, Billing presents subscription status, cards and invoice projections; paid period dates are shown only when the latest invoice is paid.
