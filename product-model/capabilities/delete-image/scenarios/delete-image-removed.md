---
{
  "kind": "primary",
  "routes": {
    "w-image": "W IMAGE"
  },
  "steps": [
    {
      "text": "The author confirms removal of selected hosted bytes.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-image": {
          "place": "web::authenticated::image"
        }
      }
    },
    {
      "text": "The selected hosted bytes are removed without rewriting existing references; the library is reached.",
      "kind": "product",
      "entities": [
        {
          "entity": "image",
          "effect": "removes"
        }
      ],
      "contexts": {
        "w-image": {
          "place": "web::authenticated::image"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#ImageDelete"
    }
  ]
}
---

# Removed

## Trigger

Removed: Delete image.

## Outcome

The selected hosted bytes are removed without rewriting existing references; the library is reached.
