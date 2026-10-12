---
{
  "kind": "primary",
  "routes": {
    "k": "K"
  },
  "steps": [
    {
      "text": "The caller requests the selected writing detail.",
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
      "text": "The bearer-key detail returns the owned title, slug, raw body, date and canonical link.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Publication date",
            "Canonical link"
          ]
        }
      ],
      "contexts": {
        "k": {
          "place": "blog-api"
        }
      },
      "actor": "author"
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

# Owned detail

## Trigger

Owned detail: Read post.

## Outcome

The bearer-key detail returns the owned title, slug, raw body, date and canonical link.
