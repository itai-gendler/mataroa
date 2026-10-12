---
{
  "kind": "edge",
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
      "text": "The email link reply fails after persistence; the saved writing remains, and repeated provider delivery can create another entry.",
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
      "text": "No successful reply is established; provider processing fails after the saved entry.",
      "kind": "condition",
      "entities": [],
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

# Email reply failed after save

## Trigger

Email reply failed after save: Create post.

## Outcome

The email link reply fails after persistence; the saved writing remains, and repeated provider delivery can create another entry.

## Edge cases

- Creation sets creation/update times and leaves broadcast completion absent; classification, links, rendering and revision fingerprint derive from the saved writing and date.
- Calendar dates affect discovery; HTML remains readable by link while undated or future-dated, and no subscriber email is sent inline.
