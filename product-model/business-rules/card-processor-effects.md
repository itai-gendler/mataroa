---
{
  "appliesTo": [
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

# Customer membership is checked for detach/default selection

Customer membership is checked for detach/default selection. Setup confirmation rather than form POST establishes attachment. Saved-card resubscription sets a default when absent. Attachment events retain an existing default; default-setting failure is logged and acknowledged. UI hiding of default-card removal is not an endpoint prohibition.
