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
      "text": "The resolved non-Premium non-grandfathered sender receives the premium-required reply and no new writing.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "email": {
          "place": "postmark-webhook"
        }
      }
    },
    {
      "text": "The threaded premium-required reply is sent to the resolved sender address.",
      "kind": "condition",
      "actor": "author",
      "entities": [],
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

# Email plan refusal

## Trigger

Email plan refusal: Create post.

## Outcome

The resolved non-Premium non-grandfathered sender receives the premium-required reply and no new writing.
