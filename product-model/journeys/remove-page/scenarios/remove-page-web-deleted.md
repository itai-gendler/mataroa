---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author confirms removal of selected static writing.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::page"
        }
      },
      "capability": "delete-page"
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
        "web": {
          "place": "web::authenticated::page"
        }
      },
      "actor": "author",
      "capability": "delete-page"
    },
    {
      "text": "Completed removal redirects the author to the remaining static-writing collection.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "delete-page",
      "contexts": {
        "web": {
          "place": "web::authenticated::page"
        }
      }
    },
    {
      "text": "The caller requests the owned static-writing collection.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::pages"
        }
      },
      "capability": "browse-pages"
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
        "web": {
          "place": "web::authenticated::pages"
        }
      },
      "actor": "author",
      "capability": "browse-pages"
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
    },
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

# Web deleted

## Trigger

Remove selected static writing and reach the remaining collection.

## Outcome

The selected static writing is removed; web redirects to the remaining collection. The owned static-writing collection presents each title and link, including hidden entries.
