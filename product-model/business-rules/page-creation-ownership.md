---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "page",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::new-page"
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

# Page creation is limited to its owner

Page creation is limited to its owner.
