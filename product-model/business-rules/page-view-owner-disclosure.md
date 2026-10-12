---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "page-views",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::analytics"
        },
        {
          "place": "web::authenticated::page"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has",
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

# Page views disclosure is limited to its owner

Page views disclosure is limited to its owner.
