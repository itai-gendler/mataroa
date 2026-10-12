---
{
  "kind": "validation",
  "routes": {
    "c-posts": "C POSTS"
  },
  "steps": [
    {
      "text": "The caller requests an owned collection, search, status or pagination selection.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "c-posts": {
          "place": "chatgpt-posts::posts"
        }
      }
    },
    {
      "text": "Missing effective read scope prevents delegated retrieval or its bridge continuation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c-posts": {
          "place": "chatgpt-posts::posts"
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

# Insufficient delegated read

## Trigger

Insufficient delegated read: Browse posts.

## Outcome

Missing effective read scope prevents delegated retrieval or its bridge continuation.
