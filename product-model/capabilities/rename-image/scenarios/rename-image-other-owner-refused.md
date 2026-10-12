---
{
  "kind": "validation",
  "routes": {
    "w-image": "W IMAGE"
  },
  "steps": [
    {
      "text": "The author submits a replacement display name.",
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
      "text": "An unowned target is refused without rename.",
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
      "target": "main/views/general.py#ImageUpdate"
    }
  ]
}
---

# Other owner refused

## Trigger

Other owner refused: Rename image.

## Outcome

An unowned target is refused without rename.
