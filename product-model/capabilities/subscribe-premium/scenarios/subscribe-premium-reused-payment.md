---
{
  "kind": "primary",
  "routes": {
    "w-subscribe-premium": "W SUBSCRIBE PREMIUM"
  },
  "steps": [
    {
      "text": "The author retries an existing incomplete subscription with an available confirmation secret.",
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
      "text": "The existing incomplete Premium subscription is reused without creating another; its identity is saved, and successful supplied payment confirmation enables Premium and Approved.",
      "kind": "product",
      "entities": [
        {
          "entity": "premium-subscription",
          "effect": "reads",
          "facts": [
            "Processor identity",
            "Status"
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

# Reused payment

## Trigger

The author retries an existing incomplete subscription with an available confirmation secret.

## Outcome

The existing incomplete Premium subscription is reused without creating another; its identity is saved, and successful supplied payment confirmation enables Premium and Approved.
