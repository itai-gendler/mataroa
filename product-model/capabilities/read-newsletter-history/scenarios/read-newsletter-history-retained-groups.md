---
{
  "kind": "primary",
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
      "text": "Current linked accounting groups show the current writing title/link, count and maximum recorded time.",
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

# Retained groups

## Trigger

Retained groups: Read newsletter history.

## Outcome

Current linked accounting groups show the current writing title/link, count and maximum recorded time.
