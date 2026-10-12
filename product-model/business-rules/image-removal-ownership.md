---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "image",
      "effect": "removes",
      "contexts": [
        {
          "place": "web::authenticated::image"
        }
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

# Image removal is limited to its owner

Image removal is limited to its owner.
