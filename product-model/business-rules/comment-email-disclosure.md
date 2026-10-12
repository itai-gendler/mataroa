---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "reads",
      "contexts": [
        {
          "place": "blog-api"
        }
      ],
      "facts": [
        "Email"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/templates/main/post_detail.html"
    }
  ]
}
---

# Comment disclosure is limited to its owner

Comment disclosure is limited to its owner.
