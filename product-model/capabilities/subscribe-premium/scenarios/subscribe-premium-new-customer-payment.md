---
{
  "kind": "primary",
  "routes": {
    "w-subscribe-premium": "W SUBSCRIBE PREMIUM"
  },
  "steps": [
    {
      "text": "The author starts initial payment without an existing external customer and follows successful confirmation.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-subscribe-premium": {
          "place": "web::authenticated::subscribe-premium"
        }
      }
    },
    {
      "kind": "product",
      "actor": "author",
      "text": "The newly created processor customer identity is saved on the Account before subscription creation.",
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
        "w-subscribe-premium": {
          "place": "web::authenticated::subscribe-premium"
        }
      }
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
        "w-subscribe-premium": {
          "place": "web::authenticated::subscribe-premium"
        }
      },
      "actor": "author"
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
    }
  ]
}
---

# New customer payment

## Trigger

The author starts initial payment without an existing external customer and follows successful confirmation.

## Outcome

A new customer and subscription are prepared and associated with the identity; successful supplied payment confirmation enables Premium and Approved.
