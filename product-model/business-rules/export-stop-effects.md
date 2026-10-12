---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "blog"
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
      "target": "main/views/general.py"
    }
  ]
}
---

# The UUID globally selects an identity, disables mail export and rotates the key before rendering

The UUID globally selects an identity, disables mail export and rotates the key before rendering. Missing Blog host context can cause rendering failure after that mutation.
