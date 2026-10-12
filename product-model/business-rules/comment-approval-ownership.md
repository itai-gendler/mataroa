---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::comment"
        },
        {
          "place": "blog-api"
        }
      ],
      "facts": [
        "Approval"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "contains",
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

# Comment modification is limited to its owner

Comment modification is limited to its owner.
