---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::export-blog"
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

# Post disclosure is limited to its owner

Post disclosure is limited to its owner. The selected export includes undated and future writing.
