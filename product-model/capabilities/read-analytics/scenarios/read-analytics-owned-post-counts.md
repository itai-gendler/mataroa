---
{
  "kind": "primary",
  "routes": {
    "w-analytics": "W ANALYTICS",
    "w-post": "W POST"
  },
  "steps": [
    {
      "text": "The author requests selected writing or path visit statistics.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-analytics": {
          "place": "web::authenticated::analytics"
        },
        "w-post": {
          "place": "web::authenticated::post"
        }
      }
    },
    {
      "text": "The selected owned writing’s 25-day daily and total request counts are presented.",
      "kind": "product",
      "entities": [
        {
          "entity": "post-views",
          "effect": "reads",
          "facts": [
            "Visit times",
            "Daily counts",
            "Total views"
          ]
        }
      ],
      "contexts": {
        "w-analytics": {
          "place": "web::authenticated::analytics"
        },
        "w-post": {
          "place": "web::authenticated::post"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#AnalyticList"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#AnalyticPostDetail"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#AnalyticPageDetail"
    }
  ]
}
---

# Owned post counts

## Trigger

Owned post counts: Read analytics.

## Outcome

The selected owned writing’s 25-day daily and total request counts are presented.
