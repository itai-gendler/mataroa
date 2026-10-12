---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-subscription",
      "effect": "changes",
      "facts": [
        "Blog association"
      ],
      "contexts": [
        {
          "place": "web::authenticated::blog-settings"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has",
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
      "target": "main/views/general.py#UserDelete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/models.py#Notification"
    }
  ]
}
---

# Only the owner clears retained enrollment associations during account closure

Only the owner clears retained enrollment associations during account closure.
