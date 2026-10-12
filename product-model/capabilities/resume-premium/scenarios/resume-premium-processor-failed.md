---
{
  "kind": "edge",
  "routes": {
    "w-premium-subscription": "W PREMIUM SUBSCRIPTION"
  },
  "steps": [
    {
      "text": "The author requests clearing a scheduled cancellation.",
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
      "text": "A caught resumption error returns service failure (503) without a confirmed schedule change or success redirect.",
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
      "target": "main/views/billing.py#BillingResume"
    }
  ]
}
---

# Processor failed

## Trigger

Processor failed: Resume premium.

## Outcome

A caught resumption error returns service failure (503) without a confirmed schedule change or success redirect.
