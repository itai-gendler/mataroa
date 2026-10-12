---
{
  "kind": "primary",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The bound caller submits reviewed title/body changes and the current revision fingerprint.",
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
      "text": "The reviewed title/body update is applied to the matching undated revision; absent fields stay unchanged and empty body clears content.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Title",
            "Markdown content",
            "Updated time",
            "Rendered content",
            "Revision fingerprint",
            "Excerpt"
          ]
        }
      ],
      "contexts": {
        "a": {
          "place": "chatgpt-agent"
        }
      },
      "actor": "ai-agent"
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
      "target": "main/mcp/server.py#ToolService"
    }
  ]
}
---

# Reviewed content saved

## Trigger

Reviewed content saved: Edit draft.

## Outcome

The reviewed title/body update is applied to the matching undated revision; absent fields stay unchanged and empty body clears content.
