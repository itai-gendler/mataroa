---
{
  "kind": "validation",
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
      "text": "Invalid configured inbound Basic credentials returns refusal without accepting a provider delivery or creating writing.",
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

# Credential or scope refusal

## Trigger

Credential or scope refusal: Create post.

## Outcome

Invalid configured inbound Basic credentials returns refusal without accepting a provider delivery or creating writing.
