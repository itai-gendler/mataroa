---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The caller supplies username and password.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::public::log-in"
        }
      },
      "capability": "log-in"
    },
    {
      "text": "Accepted credentials establish a session; absent a prior destination the index redirects to the own Blog.",
      "kind": "condition",
      "entities": [
        {
          "entity": "blog",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::log-in"
        }
      },
      "capability": "log-in"
    },
    {
      "text": "With no prior destination, login reaches the index, which redirects the author to the own writing homepage.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "log-in",
      "contexts": {
        "web": {
          "place": "web::public::log-in"
        }
      }
    },
    {
      "text": "The caller requests the resolved writing destination, feed or sitemap.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::blog"
        }
      },
      "capability": "browse-blog"
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
        "web": {
          "place": "web::authenticated::blog"
        }
      },
      "actor": "author",
      "capability": "browse-blog"
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
        "web": {
          "place": "web::authenticated::blog"
        }
      },
      "actor": "author",
      "capability": "browse-blog"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/urls.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/settings.py"
    },
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

# Default login

## Trigger

Sign in with no prior destination and reach the own Blog.

## Outcome

Accepted credentials establish a session; absent a prior destination the index redirects to the own Blog. The owner index additionally presents undated and future-dated writing.
