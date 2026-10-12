---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author supplies the Webring name and information, previous and next addresses.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::webring"
        }
      },
      "capability": "change-webring-settings"
    },
    {
      "text": "The four Webring fields are saved and the dashboard is reached.",
      "kind": "product",
      "entities": [
        {
          "entity": "blog",
          "effect": "changes",
          "facts": [
            "Webring name",
            "Webring information address",
            "Previous Webring address",
            "Next Webring address"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::webring"
        }
      },
      "actor": "author",
      "capability": "change-webring-settings"
    },
    {
      "text": "Saving Webring preferences redirects the author to the dashboard.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "change-webring-settings",
      "contexts": {
        "web": {
          "place": "web::authenticated::webring"
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
      "target": "main/views/general.py#WebringUpdate"
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

Save Webring settings and reach the dashboard.

## Outcome

The four Webring fields are saved and the dashboard is reached. The dashboard presents the current username, Blog identity, pending-response count, feature flags.
