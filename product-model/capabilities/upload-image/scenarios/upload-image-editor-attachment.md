---
{
  "kind": "primary",
  "routes": {
    "w-new-post": "W NEW POST",
    "w-post": "W POST",
    "w-new-page": "W NEW PAGE",
    "w-page": "W PAGE"
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
        "w-new-post": {
          "place": "web::authenticated::new-post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        },
        "w-new-page": {
          "place": "web::authenticated::new-page"
        },
        "w-page": {
          "place": "web::authenticated::page"
        }
      }
    },
    {
      "text": "Accepted inline attachment bytes are saved and the returned address is inserted into the writing in progress.",
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
        "w-new-post": {
          "place": "web::authenticated::new-post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        },
        "w-new-page": {
          "place": "web::authenticated::new-page"
        },
        "w-page": {
          "place": "web::authenticated::page"
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

# Editor attachment

## Trigger

Editor attachment: Upload image.

## Outcome

Accepted inline attachment bytes are saved and the returned address is inserted into the writing in progress.
