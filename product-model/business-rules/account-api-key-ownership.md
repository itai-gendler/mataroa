---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::api"
        }
      ],
      "facts": [
        "API key"
      ]
    }
  ],
  "permits": [
    {
      "related": [
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
      "target": "main/views/api.py"
    }
  ]
}
---

# Account modification is limited to its owner

Account modification is limited to its owner.
