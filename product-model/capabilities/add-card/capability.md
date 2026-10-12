---
{
  "availability": [
    {
      "place": "web::authenticated"
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
  ],
  "domain": "billing"
}
---

# Add card

Processor setup and successful confirmation attach the selected external payment method; confirmation reports completion.
