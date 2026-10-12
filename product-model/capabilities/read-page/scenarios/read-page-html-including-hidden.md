---
{
  "kind": "primary",
  "routes": {
    "p-page": "P PAGE",
    "w-page": "W PAGE"
  },
  "steps": [
    {
      "text": "The caller requests selected static-writing detail.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-page": {
          "place": "web::public::page"
        },
        "w-page": {
          "place": "web::authenticated::page"
        }
      }
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
        "p-page": {
          "place": "web::public::page"
        },
        "w-page": {
          "place": "web::authenticated::page"
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

# Html including hidden

## Trigger

Html including hidden: Read page.

## Outcome

The selected rendered static writing is readable even when hidden from listings.
