---
{
  "kind": "validation",
  "routes": {
    "w-image": "W IMAGE"
  },
  "steps": [
    {
      "text": "The author selects uploaded bytes and their management detail.",
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
      "text": "An unowned hosted-image detail is refused.",
      "kind": "condition",
      "entities": [
        {
          "entity": "image",
          "effect": "reads",
          "facts": []
        }
      ],
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
      "target": "main/views/general.py#ImageDetail"
    }
  ]
}
---

# Other owner refused

## Trigger

Other owner refused: Read image.

## Outcome

An unowned hosted-image detail is refused.
