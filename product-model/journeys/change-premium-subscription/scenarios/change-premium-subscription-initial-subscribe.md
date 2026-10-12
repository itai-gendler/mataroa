---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author with an existing external customer starts a new initial subscription and follows successful payment confirmation.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::subscribe-premium"
        }
      },
      "capability": "subscribe-premium"
    },
    {
      "text": "A missing, canceled or incomplete-expired Premium subscription is replaced by a new incomplete subscription; its identity is saved, and a successful supplied payment return enables Premium and Approved.",
      "kind": "product",
      "entities": [
        {
          "entity": "premium-subscription",
          "effect": "creates",
          "facts": [
            "Processor identity",
            "Status",
            "Paid-period start",
            "Paid-period end",
            "Cancellation scheduled"
          ]
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Current subscription",
            "Premium",
            "Approved"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::subscribe-premium"
        }
      },
      "actor": "author",
      "capability": "subscribe-premium"
    },
    {
      "text": "The completed subscription operation redirects the author to Billing.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "subscribe-premium",
      "contexts": {
        "web": {
          "place": "web::authenticated::subscribe-premium"
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
      "target": "main/views/billing.py#BillingSubscribe"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#BillingResubscribe"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_welcome"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_overview"
    }
  ]
}
---

# Initial subscribe

## Trigger

Complete subscription work and inspect Billing.

## Outcome

A missing, canceled or incomplete-expired Premium subscription is replaced by a new incomplete subscription; its identity is saved, and a successful supplied payment return enables Premium and Approved. For an existing external customer, Billing presents subscription status, cards and invoice projections; paid period dates are shown only when the latest invoice is paid.
