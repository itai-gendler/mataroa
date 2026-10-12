---
{
  "kind": "validation",
  "routes": {
    "k": "K"
  },
  "steps": [
    {
      "text": "The caller submits a title, optional body and optional calendar date with its current bearer credential.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "A missing or invalid current API bearer produces the authentication failure (403) without creating writing.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "k": {
          "place": "blog-api"
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

A missing or invalid current API bearer produces the authentication failure (403) without creating writing.
