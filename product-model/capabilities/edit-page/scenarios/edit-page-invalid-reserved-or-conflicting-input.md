---
{
  "kind": "validation",
  "routes": {
    "w-page": "W PAGE",
    "k": "K"
  },
  "steps": [
    {
      "text": "The author submits changed static-writing fields and hidden choice.",
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
      "text": "Reserved, duplicate or invalid fields prevent the requested update.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-page": {
          "place": "web::authenticated::page"
        },
        "k": {
          "place": "blog-api"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PageUpdate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_page"
    }
  ]
}
---

# Invalid reserved or conflicting input

## Trigger

Invalid reserved or conflicting input: Edit page.

## Outcome

Reserved, duplicate or invalid fields prevent the requested update.
