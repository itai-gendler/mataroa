---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author submits UTF-8 text files.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::import-posts"
        }
      },
      "capability": "import-posts"
    },
    {
      "text": "Each UTF-8 text file becomes an undated entry whose title comes from its filename; completion redirects to the Blog.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "creates",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Rendered content",
            "Canonical link",
            "Proper link",
            "Created time",
            "Updated time",
            "Publication date",
            "Publication status",
            "Discovery eligibility",
            "Revision fingerprint",
            "Broadcast completion",
            "Newsletter eligibility",
            "Excerpt"
          ]
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::import-posts"
        }
      },
      "actor": "author",
      "capability": "import-posts"
    },
    {
      "text": "Completion of the import redirects the author to the own writing homepage.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "import-posts",
      "contexts": {
        "web": {
          "place": "web::authenticated::import-posts"
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
      "target": "main/views/general.py#BlogImport"
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

# Imported

## Trigger

Import text files and inspect the resulting Blog.

## Outcome

Each UTF-8 text file becomes an undated entry whose title comes from its filename; completion redirects to the Blog. The owner index additionally presents undated and future-dated writing.
