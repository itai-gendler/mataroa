---
{
  "kind": "primary",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The bound caller submits a credential for family revocation.",
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
      "text": "An unknown credential is acknowledged without revealing whether any family exists.",
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
      "target": "mataroa/oauth.py#MataroaRevokeTokenView"
    }
  ]
}
---

# Unknown credential nondisclosure

## Trigger

Unknown credential nondisclosure: Revoke AI agent access.

## Outcome

An unknown credential is acknowledged without revealing whether any family exists.
