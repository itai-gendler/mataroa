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
      "text": "The exact spam header causes an acknowledged drop without new writing.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "email": {
          "place": "postmark-webhook"
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

# Spam email ignored

## Trigger

Spam email ignored: Create post.

## Outcome

The exact spam header causes an acknowledged drop without new writing.
