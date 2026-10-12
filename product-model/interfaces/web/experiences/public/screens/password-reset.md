---
{
  "entities": [
    {
      "entity": "account",
      "collects": [
        "Email",
        "Password credential"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/urls.py"
    }
  ]
}
---

# Password reset

Request, own emailed continuation and new password completion or invalid-link outcome.
