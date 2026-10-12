---
{
  "kind": "edge",
  "routes": {
    "w-billing": "W BILLING"
  },
  "steps": [
    {
      "text": "The author opens the billing overview.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-billing": {
          "place": "web::authenticated::billing"
        }
      }
    },
    {
      "text": "Successful customer preparation saves its external identity on the Account.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Processor customer"
          ]
        }
      ],
      "contexts": {
        "w-billing": {
          "place": "web::authenticated::billing"
        }
      },
      "actor": "author"
    },
    {
      "text": "Later processor retrieval fails, so the complete overview is not presented and the saved customer association remains.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-billing": {
          "place": "web::authenticated::billing"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_overview"
    }
  ]
}
---

# Processor failed after customer save

## Trigger

Billing creates and saves a missing external customer before a later processor lookup fails.

## Outcome

Later processor retrieval fails, so the complete overview is not presented and the saved customer association remains.
