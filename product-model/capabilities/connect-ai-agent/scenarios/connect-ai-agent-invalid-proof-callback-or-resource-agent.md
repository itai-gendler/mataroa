---
{
  "kind": "validation",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The caller begins the registered-client consent or code-exchange stage.",
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
      "text": "Invalid exact callback, resource, proof or authentication method prevents the requested protocol stage.",
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
