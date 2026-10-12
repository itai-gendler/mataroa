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
      "text": "An invalid continuation cannot change the credential.",
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

# Invalid link

## Trigger

Invalid link: Reset password.

## Outcome

An invalid continuation cannot change the credential.
