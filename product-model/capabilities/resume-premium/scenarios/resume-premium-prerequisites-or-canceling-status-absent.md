---
{
  "kind": "validation",
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
      "text": "Absent required identity/subscription data or a subscription not scheduled for cancellation prevents resumption.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-premium-subscription": {
          "place": "web::authenticated::premium-subscription"
        }
      }
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

# Prerequisites or canceling status absent

## Trigger

Prerequisites or canceling status absent: Resume premium.

## Outcome

Absent required identity/subscription data or a subscription not scheduled for cancellation prevents resumption.
