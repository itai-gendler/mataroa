---
{
  "kind": "primary",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The caller requests selected static-writing detail.",
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
      "text": "The delegated detail returns the selected owned title, slug, raw Markdown body, hidden choice and canonical link.",
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

The delegated detail returns the selected owned title, slug, raw Markdown body, hidden choice and canonical link.
