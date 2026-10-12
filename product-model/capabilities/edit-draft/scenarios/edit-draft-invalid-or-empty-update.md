---
{
  "kind": "validation",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The bound caller submits reviewed title/body changes and the current revision fingerprint.",
      "kind": "actor",
      "entities": [],
      "actor": "ai-agent",
      "contexts": {
        "a": {
          "place": "chatgpt-agent"
        }
      }
    },
    {
      "text": "Invalid title/body or a request with no update is refused.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "chatgpt-agent"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/server.py#ToolService"
    }
  ]
}
---

# Invalid or empty update

## Trigger

Invalid or empty update: Edit draft.

## Outcome

Invalid title/body or a request with no update is refused.
