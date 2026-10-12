---
{
  "kind": "primary",
  "routes": {
    "s": "S"
  },
  "steps": [
    {
      "text": "The provider delivers a paid-invoice event.",
      "kind": "actor",
      "entities": [
        {
          "entity": "invoice",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "stripe",
      "contexts": {
        "s": {
          "place": "stripe-webhook"
        }
      }
    },
    {
      "text": "An unmatched event customer is acknowledged without enabling an identity.",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#_enable_premium"
    }
  ]
}
---

# Unknown customer ignored

## Trigger

Unknown customer ignored: Activate premium.

## Outcome

An unmatched event customer is acknowledged without enabling an identity.
