---
{
  "kind": "validation",
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
      "text": "An unmatched sender or invalid destination is acknowledged and ignored, without new writing.",
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

# Unmatched email ignored

## Trigger

Unmatched email ignored: Create post.

## Outcome

An unmatched sender or invalid destination is acknowledged and ignored, without new writing.
