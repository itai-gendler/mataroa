---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "image",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::export-blog"
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

# Image disclosure is limited to its owner

Image disclosure is limited to its owner.
