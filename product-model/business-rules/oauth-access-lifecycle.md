---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "connected-application"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/oauth.py"
    }
  ]
}
---

# Consent produces a two-minute code; exchange issues one-hour access and thirty-day refresh

Consent produces a two-minute code; exchange issues one-hour access and thirty-day refresh. Rotation revokes the old token; effective scope may narrow to a subset and cannot re-expand. Valid consumed-code or rotated-refresh replay revokes the family; invalid proof does not become valid replay. Explicit revocation acts on the authenticated client’s family and unknown credentials acknowledge without disclosure.
