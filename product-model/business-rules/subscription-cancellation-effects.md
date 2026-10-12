---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "premium-subscription"
    },
    {
      "type": "entity",
      "id": "account"
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

# Cancel schedules remote period-end termination and preserves local Premium until subscription-deletion event

Cancel schedules remote period-end termination and preserves local Premium until subscription-deletion event. Resume requires cancellation already scheduled and clears it. Prerequisite dispatch can inspect identity attributes before inherited login handling; uniform graceful failure is not established.
