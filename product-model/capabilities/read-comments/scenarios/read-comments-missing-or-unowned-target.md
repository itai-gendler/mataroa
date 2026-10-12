---
{
  "kind": "validation",
  "routes": {
    "k": "K"
  },
  "steps": [
    {
      "text": "The caller requests response disclosure for the selected writing or response identity.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "A missing or unowned owner-bound response or parent selection returns not found.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "k": {
          "place": "blog-api"
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
      "target": "main/views/api.py#api_comment"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    }
  ]
}
---

# Missing or unowned target

## Trigger

Missing or unowned target: Read comments.

## Outcome

A missing or unowned owner-bound response or parent selection returns not found.
