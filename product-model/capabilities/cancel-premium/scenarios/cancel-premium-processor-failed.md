---
{
  "kind": "edge",
  "routes": {
    "w-premium-subscription": "W PREMIUM SUBSCRIPTION"
  },
  "steps": [
    {
      "text": "The author requests period-end cancellation.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-premium-subscription": {
          "place": "web::authenticated::premium-subscription"
        }
      }
    },
    {
      "text": "A caught scheduling error returns service failure (503) without a confirmed cancellation change or success redirect.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-premium-subscription": {
          "place": "web::authenticated::premium-subscription"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#BillingCancel"
    }
  ]
}
---

# Processor failed

## Trigger

Processor failed: Cancel premium.

## Outcome

A caught scheduling error returns service failure (503) without a confirmed cancellation change or success redirect.
