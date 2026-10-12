---
{
  "availability": [
    {
      "place": "stripe-webhook"
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
  ],
  "domain": "billing"
}
---

# Activate premium

A paid-invoice event with a matched customer enables Premium and Approved; only a newly enabled transition attempts its administrative mail.
