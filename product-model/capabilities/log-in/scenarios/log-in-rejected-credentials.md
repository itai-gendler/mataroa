---
{
  "kind": "validation",
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
      "text": "Rejected credentials leave the login process without an accepted session.",
      "kind": "condition",
      "entities": [],
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

# Rejected credentials

## Trigger

Rejected credentials: Log in.

## Outcome

Rejected credentials leave the login process without an accepted session.
