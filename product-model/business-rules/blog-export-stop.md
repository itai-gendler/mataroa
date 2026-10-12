---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "blog",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ],
      "facts": [
        "Mail export enabled",
        "Export-stop link"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "reader",
        "author"
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

# Blog modification is limited to Reader or Author

Blog modification is limited to Reader or Author.
