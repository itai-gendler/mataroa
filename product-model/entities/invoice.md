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

# Invoice

An independently identified Invoice. Read through Billing, not locally authored.

## Information kept

- **Processor identity** — External invoice identifier.
- **Created time** — Processor-reported invoice creation time.
- **Period start** — Processor-reported start of the invoiced period.
- **Period end** — Processor-reported end of the invoiced period.
- **Hosted link** — External hosted-invoice address.
- **PDF link** — External invoice PDF address.
