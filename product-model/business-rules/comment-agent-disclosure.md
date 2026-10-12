---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "reads",
      "contexts": [
        {
          "place": "chatgpt-agent"
        }
      ],
      "facts": [
        "Content",
        "Rendered content",
        "Name",
        "Created time",
        "Link",
        "Author marker",
        "Approval"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "contains",
          "entity": "post"
        },
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

# Comment disclosure is limited to the owner-bound AI agent with read scope

Comment disclosure is limited to the owner-bound AI agent with read scope. The consent family on the related path is selected by the current caller; another connection with the same owner is not interchangeable.
