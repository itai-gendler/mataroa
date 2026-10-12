---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "blog",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::blog-settings"
        },
        {
          "place": "web::authenticated::webring"
        },
        {
          "place": "web::authenticated::dashboard"
        },
        {
          "place": "web::authenticated::new-post"
        },
        {
          "place": "web::authenticated::post"
        },
        {
          "place": "web::authenticated::new-page"
        },
        {
          "place": "web::authenticated::page"
        }
      ],
      "facts": [
        "Custom domain",
        "Retirement destination",
        "Theme preferences",
        "Alternative post path",
        "Comments enabled",
        "Newsletter enabled",
        "Automatic backups enabled"
      ]
    }
  ],
  "permits": [
    {
      "related": [
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

# Blog disclosure is limited to its owner

Blog disclosure is limited to its owner.
