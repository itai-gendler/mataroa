---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/models.py"
    }
  ],
  "relations": [
    {
      "entity": "ai-agent",
      "verb": "delegates to",
      "cardinality": "one-to-one"
    }
  ]
}
---

# Connected application

An independently identified Connected application. Permission flags derive from effective scopes. Represents a connection family, not each token/hash row.

## Information kept

- **Application name** — Registered client name shown during consent.
- **Owner** — The exact consenting active identity.
- **Consent date** — Time the owner allowed the connection.
- **Consented permissions** — Scope set accepted when the owner creates the consent family.
- **Effective permissions** — The current token’s scope subset, which refresh can narrow but not expand beyond current effective scope.
- **Read allowed** — Effective scope includes blog:read.
- **Draft writing allowed** — Effective scope includes drafts:write.
- **Publication allowed** — Effective scope includes posts:publish.
- **Deletion allowed** — Effective scope includes posts:delete.
- **Access expiry** — Expiry of the current issued access credential, one hour after issuance.
- **Refresh expiry** — Expiry of the current issued refresh credential, thirty days after issuance.
- **Revoked** — Whether the consent family has been revoked; false on valid consent.
