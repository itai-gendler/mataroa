---
{
  "kind": "edge",
  "routes": {
    "s": "S"
  },
  "steps": [
    {
      "text": "The provider delivers a subscription-deletion event.",
      "kind": "actor",
      "entities": [],
      "actor": "stripe",
      "contexts": {
        "s": {
          "place": "stripe-webhook"
        }
      }
    },
    {
      "text": "Event-processing failure returns server error without a claimed completed result.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "s": {
          "place": "stripe-webhook"
        }
      },
      "actor": "stripe"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_stripe_webhook"
    }
  ]
}
---

# Processing failed

## Trigger

Processing failed: End premium.

## Outcome

Event-processing failure returns server error without a claimed completed result.
