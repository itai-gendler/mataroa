---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Premium",
        "Grandfathered",
        "Monero address"
      ]
    },
    {
      "entity": "premium-subscription",
      "shows": [
        "Status",
        "Paid-period start",
        "Paid-period end",
        "Cancellation scheduled"
      ]
    },
    {
      "entity": "card",
      "shows": [
        "Processor identity",
        "Brand",
        "Last digits",
        "Expiry",
        "Default"
      ]
    },
    {
      "entity": "invoice",
      "shows": [
        "Created time",
        "Period start",
        "Period end",
        "Hosted link",
        "PDF link"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py"
    }
  ]
}
---

# Billing

Current plan and external subscription status, paid-period dates, saved methods and Premium invoice links; Grandfather Plan and Monero accounts see their own forms instead.
