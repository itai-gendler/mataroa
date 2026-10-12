---
{
  "kind": "edge",
  "routes": {
    "c-post": "C POST"
  },
  "steps": [
    {
      "text": "The caller requests the selected writing detail.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "c-post": {
          "place": "chatgpt-posts::post"
        }
      }
    },
    {
      "text": "A native detail host-call failure presents an error and retry without substituting content from an earlier selection.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c-post": {
          "place": "chatgpt-posts::post"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PostDetail"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_post"
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

# Reader retrieval failed

## Trigger

Reader retrieval failed: Read post.

## Outcome

A native detail host-call failure presents an error and retry without substituting content from an earlier selection.
