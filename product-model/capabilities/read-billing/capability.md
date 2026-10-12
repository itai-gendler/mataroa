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

The processor branch prepares a customer if absent, then presents current subscription/cards and permitted invoice projections.
