---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::public::post"
        },
        {
          "place": "web::authenticated::post"
        }
      ],
      "to": "Pending"
    }
  ],
  "permits": [
    {
      "actors": [
        "reader",
        "author"
      ],
      "when": [
        {
          "entity": "blog",
          "fact": "Comments enabled",
          "is": true
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

# Comment creation is limited to a public participant while comments are enabled

Comment creation is limited to a public participant while comments are enabled.
