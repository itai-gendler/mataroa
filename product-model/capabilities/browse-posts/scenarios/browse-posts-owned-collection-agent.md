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
      "text": "The delegated collection returns paginated owned title, slug, date, status, canonical link and 240-character excerpt summaries, filtered by title/body text and publication classification.",
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
            "Excerpt",
            "Markdown content"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/server.py#_post_list"
    }
  ]
}
---

# Owned collection

## Trigger

Owned collection: Browse posts.

## Outcome

The delegated collection returns paginated owned title, slug, date, status, canonical link and 240-character excerpt summaries, filtered by title/body text and publication classification.
