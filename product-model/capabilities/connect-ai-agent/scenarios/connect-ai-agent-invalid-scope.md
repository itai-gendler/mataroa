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
      "text": "Invalid scope or absence of mandatory blog:read prevents connection.",
      "kind": "condition",
      "entities": [
        {
          "entity": "blog",
          "effect": "reads",
          "facts": []
        }
      ],
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

# Invalid scope

## Trigger

Invalid scope: Connect AI agent.

## Outcome

Invalid scope or absence of mandatory blog:read prevents connection.
