---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The caller confirms removal of the selected writing, with a fingerprint on the delegated contract.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::post"
        }
      },
      "capability": "delete-post"
    },
    {
      "text": "The selected owned writing and dependent responses/visits are removed; nullable accounting links remain. Web redirects to the remaining Blog.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "removes"
        },
        {
          "entity": "comment",
          "effect": "removes",
          "with": "post",
          "from": "Approved",
          "as": "approved-responses"
        },
        {
          "entity": "comment",
          "effect": "removes",
          "with": "post",
          "from": "Pending",
          "as": "pending-responses"
        },
        {
          "entity": "post-views",
          "effect": "removes",
          "with": "post"
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::post"
        }
      },
      "actor": "author",
      "capability": "delete-post"
    },
    {
      "text": "Completed removal redirects the author to the own writing homepage.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "delete-post",
      "contexts": {
        "web": {
          "place": "web::authenticated::post"
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
      "target": "main/views/general.py#PostDelete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_post"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
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

# Web deleted

## Trigger

Remove selected writing and reach the remaining Blog.

## Outcome

The selected owned writing and dependent responses/visits are removed; nullable accounting links remain. Web redirects to the remaining Blog. The owner index additionally presents undated and future-dated writing.
