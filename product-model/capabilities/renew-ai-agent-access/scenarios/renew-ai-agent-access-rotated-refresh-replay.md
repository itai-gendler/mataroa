---
{
  "kind": "edge",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The bound caller submits a refresh credential and optional narrowed permissions.",
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
      "text": "Reusing a rotated refresh revokes the entire family.",
      "kind": "product",
      "entities": [
        {
          "entity": "connected-application",
          "effect": "changes",
          "facts": [
            "Revoked"
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
      "target": "mataroa/oauth.py#MataroaTokenView"
    }
  ]
}
---

# Rotated refresh replay

## Trigger

Rotated refresh replay: Renew AI agent access.

## Outcome

Reusing a rotated refresh revokes the entire family.
