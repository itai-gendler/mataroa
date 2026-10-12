---
{
  "kind": "validation",
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
      "text": "Invalid, expired or ineligible refresh is refused without successful rotation.",
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
      "target": "mataroa/oauth.py#MataroaTokenView"
    }
  ]
}
---

# Expired or invalid refresh

## Trigger

Expired or invalid refresh: Renew AI agent access.

## Outcome

Invalid, expired or ineligible refresh is refused without successful rotation.
