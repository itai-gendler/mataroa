---
{
  "kind": "validation",
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
      "text": "An unowned target is refused without removal.",
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

# Other owner refused

## Trigger

Other owner refused: Delete page.

## Outcome

An unowned target is refused without removal.
