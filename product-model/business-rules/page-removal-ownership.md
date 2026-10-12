---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "page",
      "effect": "removes",
      "contexts": [
        {
          "place": "web::authenticated::page"
        },
        {
          "place": "blog-api"
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

# Page removal is limited to its owner

Page removal is limited to its owner.
