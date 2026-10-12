---
{
  "kind": "validation",
  "routes": {
    "w-new-page": "W NEW PAGE",
    "k": "K"
  },
  "steps": [
    {
      "text": "The author submits title, permalink, body and hidden choice.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-new-page": {
          "place": "web::authenticated::new-page"
        },
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "Reserved, duplicate or invalid fields prevent the requested creation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-new-page": {
          "place": "web::authenticated::new-page"
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
      "target": "main/views/general.py#PageCreate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_pages"
    }
  ]
}
---

# Invalid reserved or conflicting input

## Trigger

Invalid reserved or conflicting input: Create page.

## Outcome

Reserved, duplicate or invalid fields prevent the requested creation.
