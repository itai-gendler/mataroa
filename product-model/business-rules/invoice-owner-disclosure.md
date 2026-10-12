---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "invoice",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::billing"
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

# Invoice disclosure is limited to its owner

Invoice disclosure is limited to its owner.
