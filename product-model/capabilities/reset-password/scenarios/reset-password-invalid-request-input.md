---
{
  "kind": "validation",
  "routes": {
    "p-password-reset": "P PASSWORD RESET"
  },
  "steps": [
    {
      "text": "The caller requests a reset using an email address and follows their own continuation.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-password-reset": {
          "place": "web::public::password-reset"
        }
      }
    },
    {
      "text": "Invalid request input is presented by the configured form without completing a reset.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p-password-reset": {
          "place": "web::public::password-reset"
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

# Invalid request input

## Trigger

Invalid request input: Reset password.

## Outcome

Invalid request input is presented by the configured form without completing a reset.
