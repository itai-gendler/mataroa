---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "premium-subscription",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::premium-subscription"
        }
      ],
      "facts": [
        "Cancellation scheduled"
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
        },
        {
          "entity": "account",
          "fact": "Grandfathered",
          "is": false
        },
        {
          "entity": "account",
          "fact": "Processor customer",
          "present": true
        },
        {
          "entity": "account",
          "fact": "Current subscription",
          "present": true
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

# Premium subscription modification is limited to its eligible Premium owner

Premium subscription modification is limited to its eligible Premium owner.
