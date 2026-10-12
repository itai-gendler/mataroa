---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post-views",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::analytics"
        },
        {
          "place": "web::authenticated::post"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has",
          "entity": "post"
        },
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

# Post views disclosure is limited to its owner

Post views disclosure is limited to its owner.
