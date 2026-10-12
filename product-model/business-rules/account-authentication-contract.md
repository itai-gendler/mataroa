---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py"
    }
  ]
}
---

# Locally configured forms, routes and destinations establish session acceptance/refusal, logout, current-password change and own emailed reset continuation

Locally configured forms, routes and destinations establish session acceptance/refusal, logout, current-password change and own emailed reset continuation. Default login reaches own Blog through index; logout and deletion reach public landing information. Exact inherited expiry, enumeration and invalidation algorithms are not established by local inspection.
