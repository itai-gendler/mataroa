---
{
  "kind": "primary",
  "routes": {
    "p-blog": "P BLOG",
    "w-blog": "W BLOG"
  },
  "steps": [
    {
      "text": "The caller requests the resolved writing destination, feed or sitemap.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-blog": {
          "place": "web::public::blog"
        },
        "w-blog": {
          "place": "web::authenticated::blog"
        }
      }
    },
    {
      "text": "The feed presents the latest 100 due/past dated entries and rendered content; every feed request records a path visit.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Publication date",
            "Discovery eligibility",
            "Proper link"
          ]
        },
        {
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Title",
            "Link",
            "Hidden"
          ]
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": [
            "Title",
            "Proper address"
          ]
        }
      ],
      "contexts": {
        "p-blog": {
          "place": "web::public::blog"
        },
        "w-blog": {
          "place": "web::authenticated::blog"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#index"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/middleware.py#host_middleware"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/feeds.py#RSSBlogFeed"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/sitemaps.py"
    }
  ]
}
---

# Rss

## Trigger

Rss: Browse blog.

## Outcome

The feed presents the latest 100 due/past dated entries and rendered content; every feed request records a path visit.
