---
{
  "kind": "primary",
  "routes": {
    "w-blog": "W BLOG"
  },
  "steps": [
    {
      "text": "The caller requests the resolved writing destination, feed or sitemap.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-blog": {
          "place": "web::authenticated::blog"
        }
      }
    },
    {
      "text": "The owner index additionally presents undated and future-dated writing.",
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
        "w-blog": {
          "place": "web::authenticated::blog"
        }
      },
      "actor": "author"
    },
    {
      "text": "The stored calendar date is compared with today to classify discovery eligibility.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Discovery eligibility"
          ]
        }
      ],
      "contexts": {
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

# Owner index

## Trigger

Owner index: Browse blog.

## Outcome

The owner index additionally presents undated and future-dated writing.
