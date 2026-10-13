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
      "target": "main/views/billing.py#billing_overview"
    }
  ],
  "domain": "billing"
}
---

# Read billing

Billing shows the form the account's billing arrangement selects: the Grandfather Plan, Monero payment, or the processor overview, which prepares a customer if absent, then presents current subscription/cards and permitted invoice projections.
