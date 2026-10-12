---
{
  "kind": "edge",
  "routes": {
    "e": "E"
  },
  "steps": [
    {
      "text": "The provider delivers the inbound sender, destination, subject, text body and available message headers.",
      "kind": "actor",
      "entities": [],
      "actor": "postmark",
      "contexts": {
        "e": {
          "place": "postmark-webhook"
        }
      }
    },
    {
      "text": "Multiple identities with the sender email cause an administrative notification and server error without selecting one.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "e": {
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

# Duplicate sender account

## Trigger

Duplicate sender account: Create post.

## Outcome

Multiple identities with the sender email cause an administrative notification and server error without selecting one.
