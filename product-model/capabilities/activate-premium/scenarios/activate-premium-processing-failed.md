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
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Premium",
            "Approved"
          ]
        }
      ],
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

# Processing failed

## Trigger

A matched paid-invoice event enables a previously non-Premium identity, then its administrative notification fails.

## Outcome

The matched payment event saves Premium and Approved before administrative mail fails; the handler returns server error (500) and the saved flags remain.
