---
{
  "kind": "primary",
  "routes": {
    "w-page": "W PAGE",
    "k": "K"
  },
  "steps": [
    {
      "text": "The author confirms removal of selected static writing.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-page": {
          "place": "web::authenticated::page"
        },
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "The selected static writing is removed; web redirects to the remaining collection.",
      "kind": "product",
      "entities": [
        {
          "entity": "page",
          "effect": "removes"
        }
      ],
      "contexts": {
        "w-page": {
          "place": "web::authenticated::page"
        },
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
      "target": "main/views/general.py#PageDelete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_page"
    }
  ]
}
---

# Removed

## Trigger

Removed: Delete page.

## Outcome

The selected static writing is removed; web redirects to the remaining collection.
