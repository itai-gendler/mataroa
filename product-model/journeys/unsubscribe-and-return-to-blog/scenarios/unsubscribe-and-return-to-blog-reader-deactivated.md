---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The participant supplies an enrolled address or follows the keyed removal address.",
      "kind": "actor",
      "entities": [],
      "actor": "reader",
      "contexts": {
        "web": {
          "place": "web::public::email-subscription"
        }
      },
      "capability": "unsubscribe-by-email"
    },
    {
      "text": "A matching Blog/address enrollment becomes inactive and the Blog is reached.",
      "kind": "product",
      "entities": [
        {
          "entity": "email-subscription",
          "effect": "changes",
          "to": "Inactive",
          "facts": [
            "Active"
          ],
          "from": "Active"
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::email-subscription"
        }
      },
      "actor": "reader",
      "capability": "unsubscribe-by-email"
    },
    {
      "text": "Address deactivation redirects the participant to the selected writing homepage.",
      "kind": "product",
      "actor": "reader",
      "entities": [],
      "capability": "unsubscribe-by-email",
      "contexts": {
        "web": {
          "place": "web::public::email-subscription"
        }
      }
    },
    {
      "text": "The caller requests the resolved writing destination, feed or sitemap.",
      "kind": "actor",
      "entities": [],
      "actor": "reader",
      "contexts": {
        "web": {
          "place": "web::public::blog"
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
          "place": "web::public::blog"
        }
      },
      "actor": "reader",
      "capability": "browse-blog"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#NotificationUnsubscribe"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#notification_unsubscribe_key"
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

# Reader deactivated

## Trigger

Deactivate an address enrollment and return to the selected Blog.

## Outcome

A matching Blog/address enrollment becomes inactive and the Blog is reached. The non-owner index shows due/past dated writing and non-hidden static links.
