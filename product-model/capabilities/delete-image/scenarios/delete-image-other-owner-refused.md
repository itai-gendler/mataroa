---
{
  "kind": "validation",
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
      "text": "An unowned target is refused without removal.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-image": {
          "place": "web::authenticated::image"
        }
      }
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

# Other owner refused

## Trigger

Other owner refused: Delete image.

## Outcome

An unowned target is refused without removal.
