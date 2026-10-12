---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::post"
        }
      ],
      "to": "Approved"
    }
  ],
  "permits": [
    {
      "actors": [
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

# Comment creation is limited to Author

Comment creation is limited to Author. The signed-in caller’s author marker and username are used. The handler checks sign-in and the selected host; it adds no ownership or comments-enabled check.
