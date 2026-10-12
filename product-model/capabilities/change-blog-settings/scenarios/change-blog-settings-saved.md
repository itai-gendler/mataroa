---
{
  "kind": "primary",
  "routes": {
    "w-blog-settings": "W BLOG SETTINGS"
  },
  "steps": [
    {
      "text": "The author supplies profile and exposed writing-destination preferences.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-blog-settings": {
          "place": "web::authenticated::blog-settings"
        }
      }
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
        "w-blog-settings": {
          "place": "web::authenticated::blog-settings"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#UserUpdate"
    }
  ]
}
---

# Saved

## Trigger

A retirement-eligible author submits valid profile and Blog settings, including the exposed retirement destination.

## Outcome

The validated profile and exposed Blog fields are saved, changing addresses when username changes, then the dashboard is reached.
