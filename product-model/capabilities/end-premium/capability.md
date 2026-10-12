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
    }
  ],
  "domain": "billing"
}
---

# End premium

A matched subscription-deletion event clears local Premium and current subscription identity.
