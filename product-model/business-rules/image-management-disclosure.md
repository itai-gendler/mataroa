---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "image",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::images"
        },
        {
          "place": "web::authenticated::image"
        }
      ],
      "facts": [
        "Name",
        "Extension",
        "Address",
        "Size",
        "Uploaded time"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "contains",
          "entity": "blog"
        },
        {
          "verb": "holds",
          "entity": "account"
        },
        {
          "verb": "has",
          "entity": "author"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py"
    }
  ]
}
---

# Image disclosure is limited to its owner

Image disclosure is limited to its owner.
