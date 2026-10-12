---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author supplies profile and exposed writing-destination preferences.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::blog-settings"
        }
      },
      "capability": "change-blog-settings"
    },
    {
      "text": "The validated profile and exposed Blog fields are saved, changing addresses when username changes, then the dashboard is reached.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Username",
            "Email"
          ]
        },
        {
          "entity": "blog",
          "effect": "changes",
          "facts": [
            "Title",
            "Byline",
            "Footer",
            "Custom domain",
            "Retirement destination",
            "Theme preferences",
            "Alternative post path",
            "Comments enabled",
            "Newsletter enabled",
            "Mail export enabled"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::blog-settings"
        }
      },
      "actor": "author",
      "capability": "change-blog-settings"
    },
    {
      "text": "Saving preferences redirects the author to the dashboard.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "change-blog-settings",
      "contexts": {
        "web": {
          "place": "web::authenticated::blog-settings"
        }
      }
    },
    {
      "text": "The author opens the dashboard overview.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::dashboard"
        }
      },
      "capability": "read-dashboard"
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
        "web": {
          "place": "web::authenticated::dashboard"
        }
      },
      "actor": "author",
      "capability": "read-dashboard"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#UserUpdate"
    },
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

# Saved

## Trigger

A retirement-eligible author submits valid profile and Blog settings, including the exposed retirement destination.

## Outcome

The validated profile and exposed Blog fields are saved, changing addresses when username changes, then the dashboard is reached. The dashboard presents the current username, Blog identity, pending-response count, feature flags.
