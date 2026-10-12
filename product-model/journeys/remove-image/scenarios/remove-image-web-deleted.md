---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author confirms removal of selected hosted bytes.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::image"
        }
      },
      "capability": "delete-image"
    },
    {
      "text": "The selected hosted bytes are removed without rewriting existing references; the library is reached.",
      "kind": "product",
      "entities": [
        {
          "entity": "image",
          "effect": "removes"
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::image"
        }
      },
      "actor": "author",
      "capability": "delete-image"
    },
    {
      "text": "Completed removal redirects the author to the hosted-byte library.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "delete-image",
      "contexts": {
        "web": {
          "place": "web::authenticated::image"
        }
      }
    },
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
        "web": {
          "place": "web::authenticated::images"
        }
      },
      "capability": "browse-images"
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
        "web": {
          "place": "web::authenticated::images"
        }
      },
      "actor": "author",
      "capability": "browse-images"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#ImageDelete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#ImageList"
    }
  ]
}
---

# Web deleted

## Trigger

Remove selected hosted bytes and reach the image library.

## Outcome

The selected hosted bytes are removed without rewriting existing references; the library is reached. The owned hosted-image collection and derived count/storage amounts are presented.
