---
{
  "kind": "edge",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The bound caller submits the reviewed revision fingerprint and explicit calendar date.",
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
      "text": "A stale fingerprint refuses publication without changing the date.",
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
      "target": "main/mcp/server.py#INSTRUCTIONS"
    }
  ]
}
---

# Revision conflict

## Trigger

Revision conflict: Publish post.

## Outcome

A stale fingerprint refuses publication without changing the date.
