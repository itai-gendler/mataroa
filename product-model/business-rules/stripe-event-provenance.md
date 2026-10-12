---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account"
    },
    {
      "type": "entity",
      "id": "card"
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

# With a configured webhook secret, signature verification precedes dispatch

With a configured webhook secret, signature verification precedes dispatch. Without that secret, parsed events are accepted without a development-mode guard. Supported events use customer lookup; unknown customers/types acknowledge without entitlement mutation.
