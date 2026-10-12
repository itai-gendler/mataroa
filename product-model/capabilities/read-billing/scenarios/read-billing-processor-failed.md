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
      "text": "A processor retrieval or customer-creation exception prevents a complete overview; this run establishes no new saved customer.",
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

# Processor failed

## Trigger

Billing encounters a processor exception before saving any new customer.

## Outcome

A processor retrieval or customer-creation exception prevents a complete overview; this run establishes no new saved customer.
