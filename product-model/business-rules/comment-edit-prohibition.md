---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        },
        {
          "place": "blog-api"
        },
        {
          "place": "chatgpt-agent"
        }
      ],
      "facts": [
        "Content",
        "Name",
        "Email",
        "Author marker"
      ]
    }
  ],
  "permits": [],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py"
    }
  ]
}
---

# Comment modification is limited to nobody

Comment modification is limited to nobody.
