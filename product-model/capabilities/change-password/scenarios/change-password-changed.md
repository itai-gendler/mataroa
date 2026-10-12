---
{
  "kind": "primary",
  "routes": {
    "w-change-password": "W CHANGE PASSWORD"
  },
  "steps": [
    {
      "text": "The author supplies current and new passwords.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-change-password": {
          "place": "web::authenticated::change-password"
        }
      }
    },
    {
      "text": "The validated current and new password submission changes the credential and reaches configured completion.",
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
        "w-change-password": {
          "place": "web::authenticated::change-password"
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

# Changed

## Trigger

Changed: Change password.

## Outcome

The validated current and new password submission changes the credential and reaches configured completion.
