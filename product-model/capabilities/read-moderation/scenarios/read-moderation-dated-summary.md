---
{
  "kind": "primary",
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
      "text": "The valid selected date returns new identities/writing/responses and visit totals.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Joined date",
            "Email"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Created time",
            "Proper link"
          ]
        },
        {
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Title",
            "Created time",
            "Link"
          ]
        },
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Content",
            "Name",
            "Created time"
          ]
        },
        {
          "entity": "post-views",
          "effect": "reads",
          "facts": [
            "Visit times",
            "Daily counts",
            "Total views"
          ]
        },
        {
          "entity": "page-views",
          "effect": "reads",
          "facts": [
            "Path",
            "Visit times",
            "Daily counts",
            "Total views"
          ]
        }
      ],
      "contexts": {
        "r-summary": {
          "place": "web::restricted::summary"
        }
      },
      "actor": "administrator"
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

# Dated summary

## Trigger

Dated summary: Read moderation.

## Outcome

The valid selected date returns new identities/writing/responses and visit totals.
