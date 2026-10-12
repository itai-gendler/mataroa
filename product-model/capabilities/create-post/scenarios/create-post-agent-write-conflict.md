---
{
  "kind": "edge",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The bound caller supplies a draft title and optional text body.",
      "kind": "actor",
      "entities": [],
      "actor": "ai-agent",
      "contexts": {
        "a": {
          "place": "chatgpt-agent"
        }
      }
    },
    {
      "text": "A delegated integrity conflict returns write conflict without a completed creation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "chatgpt-agent"
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

# Agent write conflict

## Trigger

Agent write conflict: Create post.

## Outcome

A delegated integrity conflict returns write conflict without a completed creation.
