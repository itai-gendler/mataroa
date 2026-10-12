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
      "text": "The non-owner index shows due/past dated writing and non-hidden static links.",
      "kind": "product",
      "entities": [
        {
          "entity": "blog",
          "effect": "reads",
          "facts": [
            "Title",
            "Rendered byline",
            "Rendered footer",
            "Canonical address",
            "Proper address",
            "Webring name",
            "Webring information address",
            "Previous Webring address",
            "Next Webring address"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Publication date",
            "Publication status",
            "Proper link"
          ]
        },
        {
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Title",
            "Link"
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

# Visitor index

## Trigger

Visitor index: Browse blog.

## Outcome

The non-owner index shows due/past dated writing and non-hidden static links.
