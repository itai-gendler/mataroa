---
{
  "kind": "edge",
  "routes": {
    "connection": "Owner consent and delegated exchange"
  },
  "steps": [
    {
      "text": "The author reviews the registered client and consents to the requested connection.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "connection": {
          "place": "web::authenticated::connect-application"
        }
      }
    },
    {
      "text": "Owner consent creates the connection family and a two-minute authorization continuation bound to the registered client, exact callback, resource and proof challenge.",
      "kind": "product",
      "entities": [
        {
          "entity": "connected-application",
          "effect": "creates",
          "facts": [
            "Application name",
            "Owner",
            "Consent date",
            "Consented permissions",
            "Effective permissions",
            "Read allowed",
            "Draft writing allowed",
            "Publication allowed",
            "Deletion allowed",
            "Access expiry",
            "Refresh expiry",
            "Revoked"
          ]
        }
      ],
      "contexts": {
        "connection": {
          "place": "web::authenticated::connect-application"
        }
      },
      "actor": "author"
    },
    {
      "text": "The bound caller exchanges the unconsumed code using the matching client, callback, resource and PKCE proof.",
      "kind": "actor",
      "actor": "ai-agent",
      "entities": [],
      "contexts": {
        "connection": {
          "place": "chatgpt-agent"
        }
      }
    },
    {
      "text": "One-hour access and thirty-day refresh are issued for the consented family.",
      "kind": "product",
      "actor": "ai-agent",
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
        "connection": {
          "place": "chatgpt-agent"
        }
      }
    },
    {
      "text": "The bound caller reuses the consumed code with valid client and PKCE proof.",
      "kind": "actor",
      "actor": "ai-agent",
      "entities": [],
      "contexts": {
        "connection": {
          "place": "chatgpt-agent"
        }
      }
    },
    {
      "text": "The consent family is revoked and the repeated exchange is refused.",
      "kind": "product",
      "actor": "ai-agent",
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
        "connection": {
          "place": "chatgpt-agent"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/oauth.py#MataroaAuthorizationView"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/oauth.py#MataroaTokenView"
    }
  ]
}
---

# Valid code replay

## Trigger

Valid code replay: Connect AI agent.

## Outcome

Reusing a consumed valid code revokes the family and refuses another exchange; wrong proof does not invoke that replay revocation.
