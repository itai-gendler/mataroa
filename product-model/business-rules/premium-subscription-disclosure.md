---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "premium-subscription",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::billing"
        },
        {
          "place": "web::authenticated::premium-subscription"
        },
        {
          "place": "web::authenticated::subscribe-premium"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has current",
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

# Premium subscription disclosure is limited to its owner

Premium subscription disclosure is limited to its owner.
