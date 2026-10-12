---
{
  "kind": "validation",
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
      "text": "Absent entitlement/customer/current subscription or grandfathering prevents the requested cancellation.",
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
      "target": "main/views/billing.py#BillingCancel"
    }
  ]
}
---

# Prerequisites absent

## Trigger

Prerequisites absent: Cancel premium.

## Outcome

Absent entitlement/customer/current subscription or grandfathering prevents the requested cancellation.
