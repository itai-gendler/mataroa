---
{
  "kind": "primary",
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
      "text": "The native Posts view presents paginated owned title, date, status, link and excerpt summaries, with text search and Draft, Scheduled, Published or All filtering.",
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
        "c-posts": {
          "place": "chatgpt-posts::posts"
        }
      },
      "actor": "author"
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

The native Posts view presents paginated owned title, date, status, link and excerpt summaries, with text search and Draft, Scheduled, Published or All filtering.
