---
{
  "availability": [
    {
      "place": "web::authenticated"
    },
    {
      "place": "chatgpt-agent"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/oauth.py#MataroaAuthorizationView"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/oauth.py#MataroaTokenView"
    }
  ]
}
---

# Connect AI agent

The active owner consents to a registered allowed client; valid callback/resource/PKCE exchange issues bound one-hour access and thirty-day refresh credentials.
