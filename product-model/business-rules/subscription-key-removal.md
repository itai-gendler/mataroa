---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-subscription",
      "effect": "removes",
      "contexts": [
        {
          "place": "web::public::email-subscription"
        },
        {
          "place": "web::authenticated::email-subscription"
        }
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

# Email subscription removal is limited to Reader or Author

Email subscription removal is limited to Reader or Author.
