---
{
  "kind": "primary",
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
      "text": "The request sends the account-bound continuation; the same person follows it and saves a valid new credential.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Password credential"
          ]
        }
      ],
      "contexts": {
        "p-password-reset": {
          "place": "web::public::password-reset"
        }
      },
      "actor": "author"
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

# Completed own continuation

## Trigger

Completed own continuation: Reset password.

## Outcome

The request sends the account-bound continuation; the same person follows it and saves a valid new credential.
