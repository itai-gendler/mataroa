---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py"
    }
  ]
}
---

# Fingerprint binds current slug, title, body and date, distinguishing null and empty content and excluding URL

Fingerprint binds current slug, title, body and date, distinguishing null and empty content and excluding URL. Mutation checks the submitted fingerprint under the actual lock; stale revisions yield conflict without silent refresh or replay. Edit/publication require an absent existing date; deletion accepts any publication classification.
