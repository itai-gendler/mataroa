---
{
  "kind": "primary",
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
      "text": "The selected image name changes without changing its hosted address.",
      "kind": "product",
      "entities": [
        {
          "entity": "image",
          "effect": "changes",
          "facts": [
            "Name"
          ]
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
      "target": "main/views/general.py#ImageUpdate"
    }
  ]
}
---

# Name saved

## Trigger

Name saved: Rename image.

## Outcome

The selected image name changes without changing its hosted address.
