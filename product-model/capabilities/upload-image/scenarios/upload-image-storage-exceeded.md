---
{
  "kind": "validation",
  "routes": {
    "w-images": "W IMAGES",
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
        "w-images": {
          "place": "web::authenticated::images"
        },
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
      "text": "An upload that would exceed 1,000,000,000 owned bytes is refused.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-images": {
          "place": "web::authenticated::images"
        },
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

# Storage exceeded

## Trigger

Storage exceeded: Upload image.

## Outcome

An upload that would exceed 1,000,000,000 owned bytes is refused.
