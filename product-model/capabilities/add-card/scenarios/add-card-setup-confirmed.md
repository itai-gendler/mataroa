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
      "text": "Processor setup and successful confirmation attach the selected external payment method; confirmation reports completion.",
      "kind": "product",
      "entities": [
        {
          "entity": "card",
          "effect": "creates",
          "facts": [
            "Processor identity",
            "Customer association",
            "Brand",
            "Last digits",
            "Expiry",
            "Default"
          ]
        }
      ],
      "contexts": {
        "w-new-card": {
          "place": "web::authenticated::new-card"
        }
      },
      "actor": "author"
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

# Setup confirmed

## Trigger

Setup confirmed: Add card.

## Outcome

Processor setup and successful confirmation attach the selected external payment method; confirmation reports completion.
