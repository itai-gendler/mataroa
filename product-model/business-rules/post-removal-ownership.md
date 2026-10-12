---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "removes",
      "contexts": [
        {
          "place": "web::authenticated::post"
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

# Post removal is limited to its owner

Post removal is limited to its owner.
