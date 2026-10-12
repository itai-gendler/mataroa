---
{
  "kind": "edge",
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
      "text": "Setup or confirmation failure reports an error without establishing a new attachment.",
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

# Setup or confirmation failed

## Trigger

Setup or confirmation failed: Add card.

## Outcome

Setup or confirmation failure reports an error without establishing a new attachment.
