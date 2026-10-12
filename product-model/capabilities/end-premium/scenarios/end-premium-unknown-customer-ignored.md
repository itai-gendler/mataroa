---
{
  "kind": "primary",
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
      "text": "An unmatched customer is acknowledged without changing local entitlement.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "s": {
          "place": "stripe-webhook"
        }
      }
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

# Unknown customer ignored

## Trigger

Unknown customer ignored: End premium.

## Outcome

An unmatched customer is acknowledged without changing local entitlement.
