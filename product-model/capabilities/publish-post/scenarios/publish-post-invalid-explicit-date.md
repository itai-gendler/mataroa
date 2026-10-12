---
{
  "kind": "validation",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The bound caller submits the reviewed revision fingerprint and explicit calendar date.",
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
      "text": "A missing or invalid explicit date is refused.",
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
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/server.py#INSTRUCTIONS"
    }
  ]
}
---

# Invalid explicit date

## Trigger

Invalid explicit date: Publish post.

## Outcome

A missing or invalid explicit date is refused.
