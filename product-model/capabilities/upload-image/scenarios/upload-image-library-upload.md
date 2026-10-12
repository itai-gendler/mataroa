---
{
  "kind": "primary",
  "routes": {
    "w-images": "W IMAGES"
  },
  "steps": [
    {
      "text": "The author submits one or more image files through the library or writing editor.",
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
      "text": "Accepted library files are saved sequentially with generated addresses and upload times.",
      "kind": "product",
      "entities": [
        {
          "entity": "image",
          "effect": "creates",
          "facts": [
            "Name",
            "Hosted content",
            "Extension",
            "Address",
            "Size",
            "Uploaded time"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/forms.py#UploadImagesForm"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/templates/assets/drag-and-drop-upload.js"
    }
  ]
}
---

# Library upload

## Trigger

Library upload: Upload image.

## Outcome

Accepted library files are saved sequentially with generated addresses and upload times.
