---
{
  "kind": "edge",
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
      "text": "A native host-call failure presents an error and retry; superseded responses are ignored rather than replacing the current selection.",
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

# Retrieval or bridge failed

## Trigger

Retrieval or bridge failed: Browse posts.

## Outcome

A native host-call failure presents an error and retry; superseded responses are ignored rather than replacing the current selection.
