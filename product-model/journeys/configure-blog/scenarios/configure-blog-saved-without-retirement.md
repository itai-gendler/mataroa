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
      "text": "Ordinary profile and Blog settings are saved and the dashboard is reached; the existing retirement destination is unchanged.",
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

# Saved without retirement

## Trigger

An author without retirement eligibility submits valid ordinary profile and Blog settings; the retirement field is absent.

## Outcome

Ordinary profile and Blog settings are saved and the dashboard is reached; the existing retirement destination is unchanged. The dashboard presents the current username, Blog identity, pending-response count, feature flags.
