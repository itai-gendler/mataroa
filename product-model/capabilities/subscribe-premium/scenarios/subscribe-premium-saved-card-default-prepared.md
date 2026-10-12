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
      "text": "With no external default, the first saved Card is made default; a new Premium subscription is created and its identity saved, and a paid latest invoice enables Premium and Approved.",
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
          "entity": "card",
          "effect": "changes",
          "facts": [
            "Default"
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

# Saved card default prepared

## Trigger

The non-Premium author has saved methods but no external default; default preparation succeeds and the subsequent resubscription invoice is paid.

## Outcome

The first saved method becomes default, a new subscription is saved, paid-invoice evidence enables Premium and Approved, and Billing is reached.
