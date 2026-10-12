---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "page",
      "effect": "reads",
      "contexts": [
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
      "target": "main/views/api.py"
    }
  ]
}
---

# Page disclosure is limited to its owner

Page disclosure is limited to its owner.
