---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "premium-subscription",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::subscribe-premium"
        }
      ],
      "facts": [
        "Status",
        "Paid-period start",
        "Paid-period end"
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

# Premium subscription modification is limited to its owner

Premium subscription modification is limited to its owner.
