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
      "text": "Requested permissions narrow to a subset of the current effective scope; mandatory read remains and removed scope cannot be re-expanded by refresh.",
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

# Permissions narrowed

## Trigger

Permissions narrowed: Renew AI agent access.

## Outcome

Requested permissions narrow to a subset of the current effective scope; mandatory read remains and removed scope cannot be re-expanded by refresh.
