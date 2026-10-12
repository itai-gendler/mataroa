---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "connected-application",
      "effect": "changes",
      "contexts": [
        {
          "place": "chatgpt-agent"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "connects",
          "entity": "author"
        },
        {
          "verb": "connects",
          "entity": "connected-application"
        },
        {
          "verb": "delegates to",
          "entity": "ai-agent"
        }
      ],
      "when": [
        {
          "entity": "site-settings",
          "fact": "ChatGPT enabled",
          "is": true
        }
      ]
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

# Connected application modification is limited to the credential-bound AI agent

Connected application modification is limited to the credential-bound AI agent. The related path starts at the credential-selected consent family and returns through its owner to that same family and reaches its bound caller through the consenting person. Exchange, rotation, replay and revocation retain their different proof and expiry checks.
