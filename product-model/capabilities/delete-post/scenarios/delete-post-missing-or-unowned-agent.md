---
{
  "kind": "validation",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The caller confirms removal of the selected writing, with a fingerprint on the delegated contract.",
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
      "text": "A missing or unowned target is refused without removal.",
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
      "target": "main/views/general.py#PostDelete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_post"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    }
  ]
}
---

# Missing or unowned

## Trigger

Missing or unowned: Delete post.

## Outcome

A missing or unowned target is refused without removal.
