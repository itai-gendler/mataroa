---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
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

# Post disclosure is limited to its owner

Post disclosure is limited to its owner.
