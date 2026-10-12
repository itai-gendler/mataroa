---
{
  "kind": "primary",
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

# Cancellation cleared

## Trigger

Cancellation cleared: Resume premium.

## Outcome

A remotely scheduled cancellation is cleared and Billing is reached.
