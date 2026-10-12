---
{
  "kind": "primary",
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
      "text": "An explicit valid current or past date is applied to the reviewed undated revision.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Publication date",
            "Updated time",
            "Revision fingerprint",
            "Publication status",
            "Discovery eligibility",
            "Newsletter eligibility"
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
      "target": "main/mcp/server.py#INSTRUCTIONS"
    }
  ]
}
---

# Due or past date

## Trigger

Due or past date: Publish post.

## Outcome

An explicit valid current or past date is applied to the reviewed undated revision.
