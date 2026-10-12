---
{
  "kind": "edge",
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
      "text": "A stale fingerprint returns revision conflict without applying the requested update.",
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

# Revision conflict

## Trigger

Revision conflict: Edit draft.

## Outcome

A stale fingerprint returns revision conflict without applying the requested update.
