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
      "text": "Denied consent redirects with the denial result and no new consented family.",
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

# Consent denied

## Trigger

Consent denied: Connect AI agent.

## Outcome

Denied consent redirects with the denial result and no new consented family.
