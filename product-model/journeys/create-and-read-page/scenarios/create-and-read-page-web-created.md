---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author submits title, permalink, body and hidden choice.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::new-page"
        }
      },
      "capability": "create-page"
    },
    {
      "text": "Validated static writing is saved with a unique nonreserved permalink and hidden choice; web redirects to its HTML.",
      "kind": "product",
      "entities": [
        {
          "entity": "page",
          "effect": "creates",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Rendered content",
            "Link",
            "Hidden",
            "Created time",
            "Updated time"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::new-page"
        }
      },
      "actor": "author",
      "capability": "create-page"
    },
    {
      "text": "Saving new static writing redirects the author to its HTML detail.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "create-page",
      "contexts": {
        "web": {
          "place": "web::authenticated::new-page"
        }
      }
    },
    {
      "text": "The caller requests selected static-writing detail.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::page"
        }
      },
      "capability": "read-page"
    },
    {
      "text": "The selected rendered static writing is readable even when hidden from listings.",
      "kind": "product",
      "entities": [
        {
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Title",
            "Rendered content",
            "Link"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::page"
        }
      },
      "actor": "author",
      "capability": "read-page"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PageCreate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_pages"
    },
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

# Web created

## Trigger

Save new static writing and read the resulting Page.

## Outcome

Validated static writing is saved with a unique nonreserved permalink and hidden choice; web redirects to its HTML. The selected rendered static writing is readable even when hidden from listings.
