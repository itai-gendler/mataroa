---
{
  "kind": "edge",
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
      "text": "Event processing or after-mutation administrative mail failure returns server error; already persisted flags can remain.",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#_enable_premium"
    }
  ]
}
---

# Processing failed before save

## Trigger

A paid-invoice event encounters a processing exception before saving entitlement flags.

## Outcome

An event-processing exception before the flag update returns server error (500) without an established entitlement change.
