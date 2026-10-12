---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "reads",
      "contexts": [
        {
          "place": "chatgpt-agent"
        },
        {
          "place": "chatgpt-posts"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "contains",
          "entity": "blog"
        },
        {
          "verb": "holds",
          "entity": "account"
        },
        {
          "verb": "has",
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
          "entity": "account",
          "fact": "Active",
          "is": true
        },
        {
          "entity": "site-settings",
          "fact": "ChatGPT enabled",
          "is": true
        },
        {
          "entity": "connected-application",
          "fact": "Revoked",
          "is": false
        },
        {
          "entity": "connected-application",
          "fact": "Read allowed",
          "is": true
        }
      ]
    },
    {
      "related": [
        {
          "verb": "contains",
          "entity": "blog"
        },
        {
          "verb": "holds",
          "entity": "account"
        },
        {
          "verb": "has",
          "entity": "author"
        },
        {
          "verb": "connects",
          "entity": "connected-application"
        },
        {
          "verb": "connects",
          "entity": "author"
        }
      ],
      "when": [
        {
          "entity": "account",
          "fact": "Active",
          "is": true
        },
        {
          "entity": "site-settings",
          "fact": "ChatGPT enabled",
          "is": true
        },
        {
          "entity": "connected-application",
          "fact": "Revoked",
          "is": false
        },
        {
          "entity": "connected-application",
          "fact": "Read allowed",
          "is": true
        }
      ]
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

# Post disclosure is limited to the bound AI agent or owner reader

Post disclosure is limited to the bound AI agent or owner reader. The consent family on the related path is selected by the current caller; another connection with the same owner is not interchangeable. The embedded owner view also requires the caller-selected, active consent family and effective read scope. Session cookies alone grant no delegated content access.
