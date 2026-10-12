---
{
  "kind": "primary",
  "routes": {
    "email": "Email initiation and provider delivery"
  },
  "steps": [
    {
      "text": "The author sends subject and text body to the documented dated-writing or draft destination.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "email": {
          "place": "post-by-email"
        }
      }
    },
    {
      "text": "The provider delivers the inbound sender, destination, subject, text body and available message headers.",
      "kind": "actor",
      "actor": "postmark",
      "entities": [],
      "contexts": {
        "email": {
          "place": "postmark-webhook"
        }
      }
    },
    {
      "text": "Eligible subject/text email to the post destination saves today’s dated writing and attempts a threaded link reply.",
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
        "email": {
          "place": "postmark-webhook"
        }
      },
      "actor": "postmark"
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
        "email": {
          "place": "post-by-email"
        }
      }
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
    }
  ]
}
---

# Emailed post

## Trigger

Emailed post: Create post.

## Outcome

Eligible subject/text email to the post destination saves today’s dated writing and attempts a threaded link reply.

## Edge cases

- Creation sets creation/update times and leaves broadcast completion absent; classification, links, rendering and revision fingerprint derive from the saved writing and date.
- Calendar dates affect discovery; HTML remains readable by link while undated or future-dated, and no subscriber email is sent inline.
