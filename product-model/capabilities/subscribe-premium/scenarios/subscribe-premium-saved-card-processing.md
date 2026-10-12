---
{
  "kind": "primary",
  "routes": {
    "w-subscribe-premium": "W SUBSCRIBE PREMIUM"
  },
  "steps": [
    {
      "text": "The author begins initial payment or saved-method resubscription and follows confirmation.",
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
      "text": "A new Premium subscription and current association are saved; the latest invoice is not paid, so the processing message precedes the Billing redirect without enabling local entitlement.",
      "kind": "product",
      "entities": [
        {
          "entity": "premium-subscription",
          "effect": "creates",
          "facts": [
            "Processor identity",
            "Status",
            "Paid-period start",
            "Paid-period end",
            "Cancellation scheduled"
          ]
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Current subscription"
          ]
        },
        {
          "entity": "invoice",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "w-subscribe-premium": {
          "place": "web::authenticated::subscribe-premium"
        }
      },
      "actor": "author"
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

# Saved card processing

## Trigger

The non-Premium author resubscribes with an existing customer and default method; the created subscription has no paid latest invoice.

## Outcome

The new subscription association persists while Premium and Approved stay unchanged; Billing is reached with the processing message.
