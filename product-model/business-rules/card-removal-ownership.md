---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "card",
      "effect": "removes",
      "contexts": [
        {
          "place": "web::authenticated::card"
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

# Card removal is limited to its owner

Card removal is limited to its owner. Selected membership is checked against the identity’s external customer. Hidden removal controls do not close a grant the endpoint allows.
