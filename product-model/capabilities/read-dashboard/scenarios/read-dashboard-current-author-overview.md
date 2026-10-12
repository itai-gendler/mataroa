---
{
  "kind": "primary",
  "routes": {
    "w-dashboard": "W DASHBOARD"
  },
  "steps": [
    {
      "text": "The author opens the dashboard overview.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-dashboard": {
          "place": "web::authenticated::dashboard"
        }
      }
    },
    {
      "text": "The dashboard presents the current username, Blog identity, pending-response count and feature flags.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Premium",
            "Grandfathered"
          ]
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": [
            "Title",
            "Comments enabled",
            "Newsletter enabled",
            "Automatic backups enabled"
          ]
        },
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Approval"
          ]
        }
      ],
      "contexts": {
        "w-dashboard": {
          "place": "web::authenticated::dashboard"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#dashboard"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/templates/main/dashboard.html"
    }
  ]
}
---

# Current author overview

## Trigger

Current author overview: Read dashboard.

## Outcome

The dashboard presents the current username, Blog identity, pending-response count, feature flags.
