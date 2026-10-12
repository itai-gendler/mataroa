---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "changes",
      "contexts": [
        {
          "place": "chatgpt-agent"
        }
      ],
      "facts": [
        "Title",
        "Markdown content"
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
        },
        {
          "entity": "connected-application",
          "fact": "Draft writing allowed",
          "is": true
        },
        {
          "fact": "Publication date",
          "absent": true
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

# Post modification is limited to the owner-bound AI agent with draft scope

Post modification is limited to the owner-bound AI agent with draft scope. The consent family on the related path is selected by the current caller; another connection with the same owner is not interchangeable.
