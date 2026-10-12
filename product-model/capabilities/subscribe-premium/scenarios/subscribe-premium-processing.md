---
{
  "kind": "primary",
  "routes": {
    "w-subscribe-premium": "W SUBSCRIBE PREMIUM"
  },
  "steps": [
    {
      "text": "The author follows a payment return whose supplied intent is processing.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-subscribe-premium": {
          "place": "web::authenticated::subscribe-premium"
        }
      }
    },
    {
      "text": "A processing payment outcome reports processing without establishing activation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-subscribe-premium": {
          "place": "web::authenticated::subscribe-premium"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#BillingSubscribe"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#BillingResubscribe"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_welcome"
    }
  ]
}
---

# Processing

## Trigger

The author follows a payment return whose supplied intent is processing.

## Outcome

A processing payment outcome reports processing without establishing activation.
