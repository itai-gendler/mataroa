---
{
  "kind": "primary",
  "routes": {
    "w-new-card": "W NEW CARD"
  },
  "steps": [
    {
      "text": "The author begins external payment-method setup and follows confirmation.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-new-card": {
          "place": "web::authenticated::new-card"
        }
      }
    },
    {
      "text": "A form submission or processing confirmation reports processing without establishing attachment.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-new-card": {
          "place": "web::authenticated::new-card"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#BillingCard"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_card_confirm"
    }
  ]
}
---

# Processing

## Trigger

Processing: Add card.

## Outcome

A form POST or processing confirmation reports processing without establishing attachment.
