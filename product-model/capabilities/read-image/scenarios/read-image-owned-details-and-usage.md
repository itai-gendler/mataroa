---
{
  "kind": "primary",
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
      "text": "Selected owned hosted bytes, name, address, upload time and detected usage in writing are presented.",
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
            "Uploaded time"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Markdown content",
            "Proper link"
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
      "target": "main/views/general.py#ImageDetail"
    }
  ]
}
---

# Owned details and usage

## Trigger

Owned details and usage: Read image.

## Outcome

Selected owned hosted bytes, name, address, upload time and detected usage in writing are presented.
