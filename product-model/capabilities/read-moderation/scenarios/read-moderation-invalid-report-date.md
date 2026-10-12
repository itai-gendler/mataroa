---
{
  "kind": "validation",
  "routes": {
    "r-summary": "R SUMMARY"
  },
  "steps": [
    {
      "text": "The administrator selects the report, filter or reporting date.",
      "kind": "actor",
      "entities": [],
      "actor": "administrator",
      "contexts": {
        "r-summary": {
          "place": "web::restricted::summary"
        }
      }
    },
    {
      "text": "An invalid summary date returns not found.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r-summary": {
          "place": "web::restricted::summary"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/moderation.py"
    }
  ]
}
---

# Invalid report date

## Trigger

Invalid report date: Read moderation.

## Outcome

An invalid summary date returns not found.
