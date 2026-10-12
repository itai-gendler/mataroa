---
{
  "kind": "primary",
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
        "w-new-page": {
          "place": "web::authenticated::new-page"
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

# Created

## Trigger

Created: Create page.

## Outcome

Validated static writing is saved with a unique nonreserved permalink and hidden choice; web redirects to its HTML.

## Edge cases

- Creation establishes ownership and creation/update times; omitted hidden choice is false and API omitted body is empty. Web body storage and API cleanup differ.
