---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "image",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::image"
        }
      ],
      "facts": [
        "Name"
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

# Image modification is limited to its owner

Image modification is limited to its owner.
