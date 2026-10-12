---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "page",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::page"
        },
        {
          "place": "blog-api"
        }
      ],
      "facts": [
        "Title",
        "Slug",
        "Markdown content",
        "Hidden"
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

# Page modification is limited to its owner

Page modification is limited to its owner.
