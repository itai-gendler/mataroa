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
      "text": "An already dated target is refused by the draft-publication operation.",
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

# Already dated

## Trigger

Already dated: Publish post.

## Outcome

An already dated target is refused by the draft-publication operation.
