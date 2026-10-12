---
{
  "kind": "primary",
  "routes": {
    "w-analytics": "W ANALYTICS",
    "w-page": "W PAGE"
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
        "w-page": {
          "place": "web::authenticated::page"
        }
      }
    },
    {
      "text": "The selected owned Blog/index/RSS path’s 25-day daily and total request counts are presented; they are not unique visitors.",
      "kind": "product",
      "entities": [
        {
          "entity": "page-views",
          "effect": "reads",
          "facts": [
            "Path",
            "Visit times",
            "Daily counts",
            "Total views"
          ]
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "w-analytics": {
          "place": "web::authenticated::analytics"
        },
        "w-page": {
          "place": "web::authenticated::page"
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

# Owned blog page or rss path counts

## Trigger

Owned blog page or rss path counts: Read analytics.

## Outcome

The selected owned Blog/index/RSS path’s 25-day daily and total request counts are presented; they are not unique visitors.
