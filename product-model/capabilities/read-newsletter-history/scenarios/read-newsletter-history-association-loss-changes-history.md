---
{
  "kind": "edge",
  "routes": {
    "w-newsletter": "W NEWSLETTER"
  },
  "steps": [
    {
      "text": "The author requests retained recipient-accounting groups.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-newsletter": {
          "place": "web::authenticated::newsletter"
        }
      }
    },
    {
      "text": "Removing associations changes or removes owner-visible groups; retained orphan accounting can still contribute to administrative totals.",
      "kind": "product",
      "entities": [
        {
          "entity": "newsletter-history",
          "effect": "reads",
          "facts": [
            "Post association",
            "Blog/subscriber association",
            "Current Post title",
            "Current Post link",
            "Recorded date",
            "Recipient count",
            "Retained accounting count"
          ]
        }
      ],
      "contexts": {
        "w-newsletter": {
          "place": "web::authenticated::newsletter"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#NotificationRecordList"
    }
  ]
}
---

# Association loss changes history

## Trigger

Association loss changes history: Read newsletter history.

## Outcome

Removing associations changes or removes owner-visible groups; retained orphan accounting can still contribute to administrative totals.
