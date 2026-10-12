---
{
  "kind": "primary",
  "routes": {
    "k": "K"
  },
  "steps": [
    {
      "text": "The caller requests selected static-writing detail.",
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
      "text": "The bearer-key detail returns the selected owned title, slug, raw Markdown body, hidden choice and canonical link.",
      "kind": "product",
      "entities": [
        {
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Hidden",
            "Link"
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
      "target": "main/views/general.py#PageDetail"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_page"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    }
  ]
}
---

# Owned detail

## Trigger

Owned detail: Read page.

## Outcome

The bearer-key detail returns the selected owned title, slug, raw Markdown body, hidden choice and canonical link.
