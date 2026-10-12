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

# Saved without retirement

## Trigger

An author without retirement eligibility submits valid ordinary profile and Blog settings; the retirement field is absent.

## Outcome

Ordinary profile and Blog settings are saved and the dashboard is reached; the existing retirement destination is unchanged.
