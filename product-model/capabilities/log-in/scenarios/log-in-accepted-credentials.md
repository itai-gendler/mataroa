---
{
  "kind": "primary",
  "routes": {
    "p-log-in": "P LOG IN"
  },
  "steps": [
    {
      "text": "The caller supplies username and password.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-log-in": {
          "place": "web::public::log-in"
        }
      }
    },
    {
      "text": "Accepted credentials establish a session; absent a prior destination the index redirects to the own Blog.",
      "kind": "condition",
      "entities": [
        {
          "entity": "blog",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "p-log-in": {
          "place": "web::public::log-in"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/urls.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/settings.py"
    }
  ]
}
---

# Accepted credentials

## Trigger

Accepted credentials: Log in.

## Outcome

Accepted credentials establish a session; absent a prior destination the index redirects to the own Blog.
