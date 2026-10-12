---
{
  "availability": [
    {
      "place": "chatgpt-agent"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/oauth.py#MataroaTokenView"
    }
  ]
}
---

# Renew AI agent access

A valid refresh rotates to a new access/refresh pair and revokes the previous token while retaining family consent.
