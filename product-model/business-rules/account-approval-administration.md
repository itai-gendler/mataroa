---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::restricted::users"
        }
      ],
      "facts": [
        "Approved"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "administrator"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/moderation.py"
    }
  ]
}
---

# Account modification is limited to Administrator

Account modification is limited to Administrator.
