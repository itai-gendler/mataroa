---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::post"
        },
        {
          "place": "blog-api"
        }
      ],
      "facts": [
        "Title",
        "Slug",
        "Markdown content",
        "Publication date"
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

# Post modification is limited to its owner

Post modification is limited to its owner.
