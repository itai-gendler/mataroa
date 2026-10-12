---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::new-post"
        },
        {
          "place": "web::authenticated::import-posts"
        },
        {
          "place": "blog-api"
        },
        {
          "place": "post-by-email"
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

# Post creation is limited to its owner

Post creation is limited to its owner. Subject/text email creation additionally meets the separate entitlement gate.
