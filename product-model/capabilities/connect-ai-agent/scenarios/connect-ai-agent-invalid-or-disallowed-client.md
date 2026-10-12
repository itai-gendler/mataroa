---
{
  "kind": "validation",
  "routes": {
    "w-connect-application": "W CONNECT APPLICATION"
  },
  "steps": [
    {
      "text": "The caller begins the registered-client consent or code-exchange stage.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-connect-application": {
          "place": "web::authenticated::connect-application"
        }
      }
    },
    {
      "text": "Unknown, disabled or disallowed client registration prevents the connection.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-connect-application": {
          "place": "web::authenticated::connect-application"
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

# Invalid or disallowed client

## Trigger

Invalid or disallowed client: Connect AI agent.

## Outcome

Unknown, disabled or disallowed client registration prevents the connection.
