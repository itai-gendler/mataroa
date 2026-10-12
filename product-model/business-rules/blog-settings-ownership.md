---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "blog",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::blog-settings"
        },
        {
          "place": "web::authenticated::webring"
        }
      ],
      "facts": [
        "Title",
        "Byline",
        "Footer",
        "Custom domain",
        "Theme preferences",
        "Alternative post path",
        "Comments enabled",
        "Newsletter enabled",
        "Mail export enabled",
        "Webring name",
        "Webring information address",
        "Previous Webring address",
        "Next Webring address"
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

# Blog modification is limited to its owner

Blog modification is limited to its owner.
