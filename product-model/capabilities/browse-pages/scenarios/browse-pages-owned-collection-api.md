---
{
  "kind": "primary",
  "routes": {
    "k": "K"
  },
  "steps": [
    {
      "text": "The caller requests the owned static-writing collection.",
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
      "text": "The bearer-key collection includes title, slug, raw body, hidden choice and link for every owned static entry.",
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
      "target": "main/views/general.py#PageList"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_pages"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    }
  ]
}
---

# Owned collection

## Trigger

Owned collection: Browse pages.

## Outcome

The bearer-key collection includes title, slug, raw body, hidden choice and link for every owned static entry.
