---
{
  "kind": "primary",
  "routes": {
    "w-pages": "W PAGES"
  },
  "steps": [
    {
      "text": "The caller requests the owned static-writing collection.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-pages": {
          "place": "web::authenticated::pages"
        }
      }
    },
    {
      "text": "The owned static-writing collection presents each title and link, including hidden entries.",
      "kind": "product",
      "entities": [
        {
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Title",
            "Link"
          ]
        }
      ],
      "contexts": {
        "w-pages": {
          "place": "web::authenticated::pages"
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

The owned static-writing collection presents each title and link, including hidden entries.
