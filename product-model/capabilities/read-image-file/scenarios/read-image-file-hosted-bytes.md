---
{
  "kind": "primary",
  "routes": {
    "p": "P",
    "w": "W"
  },
  "steps": [
    {
      "text": "The caller requests the hosted byte address and extension.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p": {
          "place": "web::public"
        },
        "w": {
          "place": "web::authenticated"
        }
      }
    },
    {
      "text": "A globally selected hosted address returns the stored bytes with its matching extension.",
      "kind": "product",
      "entities": [
        {
          "entity": "image",
          "effect": "reads",
          "facts": [
            "Hosted content",
            "Extension"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public"
        },
        "w": {
          "place": "web::authenticated"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#image_raw"
    }
  ]
}
---

# Hosted bytes

## Trigger

Hosted bytes: Read image file.

## Outcome

A globally selected hosted address returns the stored bytes with its matching extension.
