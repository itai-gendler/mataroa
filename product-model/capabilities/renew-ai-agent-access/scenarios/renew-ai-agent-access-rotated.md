---
{
  "kind": "primary",
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
      "text": "A valid refresh rotates to a new access/refresh pair and revokes the previous token while retaining family consent.",
      "kind": "product",
      "entities": [
        {
          "entity": "connected-application",
          "effect": "changes",
          "facts": [
            "Effective permissions",
            "Read allowed",
            "Draft writing allowed",
            "Publication allowed",
            "Deletion allowed",
            "Access expiry",
            "Refresh expiry"
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

# Rotated

## Trigger

Rotated: Renew AI agent access.

## Outcome

A valid refresh rotates to a new access/refresh pair and revokes the previous token while retaining family consent.
