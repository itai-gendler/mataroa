---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "card",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::billing"
        },
        {
          "place": "web::authenticated::card"
        },
        {
          "place": "web::authenticated::subscribe-premium"
        },
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

# Card disclosure is limited to its owner

Card disclosure is limited to its owner.
