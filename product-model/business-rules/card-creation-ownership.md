---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "card",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::new-card"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has",
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
      "target": "main/views/billing.py"
    }
  ]
}
---

# Card creation is limited to its owner

Card creation is limited to its owner.
