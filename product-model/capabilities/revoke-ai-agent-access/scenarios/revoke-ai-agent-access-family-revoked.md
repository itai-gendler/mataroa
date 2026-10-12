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
      "text": "A credential bound to the authenticated client revokes its entire connection family.",
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
      "target": "mataroa/oauth.py#MataroaRevokeTokenView"
    }
  ]
}
---

# Family revoked

## Trigger

Family revoked: Revoke AI agent access.

## Outcome

A credential bound to the authenticated client revokes its entire connection family.
