---
{
  "availability": [
    {
      "place": "web::authenticated"
    },
    {
      "place": "stripe-webhook"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_card_default"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_stripe_webhook"
    }
  ],
  "domain": "billing"
}
---

# Make card default

The selected customer-owned method becomes the default and Billing is reached.
