---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py"
    }
  ]
}
---

# Card

An independently identified Card. Externally maintained.

## Information kept

- **Processor identity** — External payment-method identifier used for selected removal and default changes.
- **Customer association** — External customer that owns the payment method.
- **Brand** — Processor-reported payment-card brand.
- **Last digits** — Processor-reported last four digits.
- **Expiry** — Processor-reported expiry month and year.
- **Default** — Whether the external customer uses this method as its invoice default.
