---
{
  "kind": "primary",
  "routes": {
    "w-images": "W IMAGES"
  },
  "steps": [
    {
      "text": "The author opens the hosted-image library.",
      "kind": "actor",
      "entities": [
        {
          "entity": "image",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "author",
      "contexts": {
        "w-images": {
          "place": "web::authenticated::images"
        }
      }
    },
    {
      "text": "The owned hosted-image collection and derived count/storage amounts are presented.",
      "kind": "product",
      "entities": [
        {
          "entity": "image",
          "effect": "reads",
          "facts": [
            "Name",
            "Hosted content",
            "Extension",
            "Address",
            "Size",
            "Uploaded time"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Image count",
            "Storage used",
            "Storage remaining"
          ]
        }
      ],
      "contexts": {
        "w-images": {
          "place": "web::authenticated::images"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#ImageList"
    }
  ]
}
---

# Library and storage

## Trigger

Library and storage: Browse images.

## Outcome

The owned hosted-image collection and derived count/storage amounts are presented.
