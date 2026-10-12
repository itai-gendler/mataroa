---
{
  "kind": "validation",
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
      "text": "Invalid current password, mismatch or local validation errors leave the credential unchanged.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-change-password": {
          "place": "web::authenticated::change-password"
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

# Invalid submission

## Trigger

Invalid submission: Change password.

## Outcome

Invalid current password, mismatch or local validation errors leave the credential unchanged.
