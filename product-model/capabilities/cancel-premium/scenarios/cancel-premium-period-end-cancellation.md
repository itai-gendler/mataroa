---
{
  "kind": "primary",
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
      "text": "Remote cancellation is scheduled at period end, administrative mail is attempted and local Premium remains until a deletion event.",
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
      "target": "main/views/billing.py#BillingCancel"
    }
  ]
}
---

# Period end cancellation

## Trigger

Period end cancellation: Cancel premium.

## Outcome

Remote cancellation is scheduled at period end, administrative mail is attempted and local Premium remains until a deletion event.
