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

# Premium subscription

An independently identified Premium subscription. Externally maintained; no invented local state machine.

## Information kept

- **Processor identity** — External current subscription identifier.
- **Status** — Processor-reported status; Billing presents canceling when cancellation is scheduled.
- **Paid-period start** — Start of the external subscription item period, displayed when the latest invoice is paid.
- **Paid-period end** — End of the external subscription item period, displayed when the latest invoice is paid.
- **Cancellation scheduled** — Whether the external subscription is set to cancel at period end.
