---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::comments-pending"
        },
        {
          "place": "web::authenticated::comment"
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

# Comment disclosure is limited to its owner

Comment disclosure is limited to its owner.
