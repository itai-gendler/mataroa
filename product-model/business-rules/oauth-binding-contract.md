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

# Only registered allowlisted clients, exact registered HTTPS callbacks, the canonical resource and S256 PKCE are accepted

Only registered allowlisted clients, exact registered HTTPS callbacks, the canonical resource and S256 PKCE are accepted. Client authentication method and proof must match. blog:read is mandatory; only the fixed supported additional scopes are accepted. The selected connection family remains bound to caller and owner, not any family sharing that owner.
