---
{
  "kind": "primary",
  "routes": {
    "w-post": "W POST"
  },
  "steps": [
    {
      "text": "The caller requests raw Markdown at the selected writing address.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-post": {
          "place": "web::authenticated::post"
        }
      }
    },
    {
      "text": "The owner receives raw Markdown for undated or future-dated writing.",
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

# Owned unpublished source

## Trigger

Owned unpublished source: Read post source.

## Outcome

The owner receives raw Markdown for undated or future-dated writing.
