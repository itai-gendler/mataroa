---
{
  "kind": "primary",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The caller requests the owned static-writing collection.",
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
      "text": "The delegated static-writing collection searches title and body, includes hidden entries, and returns paginated title, slug, hidden choice and link summaries without raw body.",
      "kind": "product",
      "entities": [
        {
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Link",
            "Hidden"
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

The delegated static-writing collection searches title and body, includes hidden entries, and returns paginated title, slug, hidden choice and link summaries without raw body.
