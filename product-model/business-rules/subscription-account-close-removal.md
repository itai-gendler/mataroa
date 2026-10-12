---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "premium-subscription",
      "effect": "removes",
      "contexts": [
        {
          "place": "web::authenticated::blog-settings"
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
      ],
      "when": [
        {
          "entity": "account",
          "fact": "Premium",
          "is": true
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

# Premium subscription removal is limited to its Premium owner

Premium subscription removal is limited to its Premium owner.
