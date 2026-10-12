---
{
  "kind": "primary",
  "routes": {
    "p-post": "P POST",
    "w-post": "W POST"
  },
  "steps": [
    {
      "text": "The caller requests raw Markdown at the selected writing address.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-post": {
          "place": "web::public::post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        }
      }
    },
    {
      "text": "Due/past dated writing returns raw Markdown.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Markdown content"
          ]
        }
      ],
      "contexts": {
        "p-post": {
          "place": "web::public::post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#post_raw"
    }
  ]
}
---

# Published source

## Trigger

Published source: Read post source.

## Outcome

Due/past dated writing returns raw Markdown.
