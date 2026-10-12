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
      "text": "Invalid exact callback, resource, proof or authentication method prevents the requested protocol stage.",
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

# Invalid proof callback or resource

## Trigger

Invalid proof callback or resource: Connect AI agent.

## Outcome

Invalid exact callback, resource, proof or authentication method prevents the requested protocol stage.
