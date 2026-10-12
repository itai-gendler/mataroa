---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account"
    },
    {
      "type": "entity",
      "id": "post"
    },
    {
      "type": "entity",
      "id": "page"
    },
    {
      "type": "entity",
      "id": "comment"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py"
    }
  ]
}
---

# The current bearer key resolves the owner without an active-account check

The current bearer key resolves the owner without an active-account check. Replacing the key prevents the previous bearer from resolving. Owned selection governs Post/Page/Comment access, with contract-specific validation and serialization.
