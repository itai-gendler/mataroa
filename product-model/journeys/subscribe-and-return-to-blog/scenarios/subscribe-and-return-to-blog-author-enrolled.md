---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The participant supplies an email address for enrollment.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::email-subscription"
        }
      },
      "capability": "subscribe-by-email"
    },
    {
      "text": "A new selected-Blog email enrollment is immediately active and the Blog is reached, without a confirmation round trip.",
      "kind": "product",
      "entities": [
        {
          "entity": "email-subscription",
          "effect": "creates",
          "to": "Active",
          "facts": [
            "Blog association",
            "Email",
            "Unsubscribe link",
            "Active"
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
          "place": "web::authenticated::email-subscription"
        }
      },
      "actor": "author",
      "capability": "subscribe-by-email"
    },
    {
      "text": "Successful enrollment redirects the participant to the selected writing homepage.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "subscribe-by-email",
      "contexts": {
        "web": {
          "place": "web::authenticated::email-subscription"
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
      "target": "main/views/general.py#Notification"
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

# Author enrolled

## Trigger

Enroll by email and return to the selected Blog.

## Outcome

A new selected-Blog email enrollment is immediately active and the Blog is reached, without a confirmation round trip. The non-owner index shows due/past dated writing and non-hidden static links.
