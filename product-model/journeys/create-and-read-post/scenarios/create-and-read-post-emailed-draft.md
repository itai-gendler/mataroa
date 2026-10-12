---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author sends subject and text body to the documented dated-writing or draft destination.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "post-by-email"
        }
      },
      "capability": "create-post"
    },
    {
      "text": "The provider delivers the inbound sender, destination, subject, text body and available message headers.",
      "kind": "actor",
      "actor": "postmark",
      "entities": [],
      "contexts": {
        "web": {
          "place": "postmark-webhook"
        }
      },
      "capability": "create-post"
    },
    {
      "text": "Eligible subject/text email to the draft destination saves undated writing and attempts a threaded link reply.",
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
        }
      ],
      "contexts": {
        "web": {
          "place": "postmark-webhook"
        }
      },
      "actor": "postmark",
      "capability": "create-post"
    },
    {
      "text": "The sender receives the saved writing address in a reply threaded when the original message identifier is present.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Canonical link"
          ]
        }
      ],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "post-by-email"
        }
      },
      "capability": "create-post"
    },
    {
      "text": "The sender receives their own saved-writing link in the reply and follows it to the HTML detail.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "create-post",
      "contexts": {
        "web": {
          "place": "post-by-email"
        }
      }
    },
    {
      "text": "The caller requests the selected writing detail.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::post"
        }
      },
      "capability": "read-post"
    },
    {
      "text": "An undated or future-dated HTML link still renders with the unpublished status notice.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Rendered content",
            "Publication date",
            "Publication status",
            "Proper link"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::post"
        }
      },
      "actor": "author",
      "capability": "read-post"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PostCreate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_posts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#postmark_webhook"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PostDetail"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_post"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/static/mcp/posts.js"
    }
  ]
}
---

# Emailed draft

## Trigger

Save new writing and follow the product’s redirect or own email reply to read it.

## Outcome

Eligible subject/text email to the draft destination saves undated writing and attempts a threaded link reply. An undated or future-dated HTML link still renders with the unpublished status notice.
