---
{
  "kind": "primary",
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
      "text": "Validated static-writing fields and hidden choice persist; web retains the selected subject.",
      "kind": "product",
      "entities": [
        {
          "entity": "page",
          "effect": "changes",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Hidden",
            "Updated time",
            "Rendered content",
            "Link"
          ]
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

# Saved

## Trigger

Saved: Edit page.

## Outcome

Validated static-writing fields and hidden choice persist; web retains the selected subject.
