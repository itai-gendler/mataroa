---
{
  "kind": "primary",
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
      "text": "A valid search or selection with no matches returns an empty collection.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Publication date",
            "Publication status",
            "Canonical link",
            "Proper link"
          ]
        }
      ],
      "contexts": {
        "a": {
          "place": "chatgpt-agent"
        }
      },
      "actor": "ai-agent"
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

# Empty result

## Trigger

Empty result: Browse posts.

## Outcome

A valid search or selection with no matches returns an empty collection.
