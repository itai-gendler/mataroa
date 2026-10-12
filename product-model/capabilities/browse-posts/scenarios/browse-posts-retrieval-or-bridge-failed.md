---
{
  "kind": "edge",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The caller requests an owned collection, search, status or pagination selection.",
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
      "text": "A delegated dependency or transport failure returns the tool error without a successful collection.",
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
      "target": "main/views/api.py#api_posts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/static/mcp/posts.js"
    }
  ]
}
---

# Retrieval or bridge failed

## Trigger

Retrieval or bridge failed: Browse posts.

## Outcome

A delegated dependency or transport failure returns the tool error without a successful collection.
