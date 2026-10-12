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
      "text": "With a saved default method, a new Premium subscription is created and its identity saved; a paid latest invoice enables Premium and Approved before returning to Billing.",
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
            "Current subscription",
            "Premium",
            "Approved"
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

# Saved card resubscription

## Trigger

The non-Premium author resubscribes using an existing external customer and saved default method; the resulting latest invoice is paid.

## Outcome

A new subscription and current association are saved, paid-invoice evidence enables Premium and Approved, and Billing is reached without changing the existing default.

## Edge cases

- If there is no default and default preparation fails, the error is logged and the resubscription form still renders without a default summary; a later creation attempt can proceed.
