---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-subscription"
    },
    {
      "type": "entity",
      "id": "blog"
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

# Enrollment is immediately active without address verification

Enrollment is immediately active without address verification. Blog/address identity is unique; inactive enrollment reactivates and active duplicates produce validation. Address unsubscribe changes Active; keyed unsubscribe deletes a global key-selected target after requiring a Blog host. Nullable Blog and accounting links can survive parent deletion.
