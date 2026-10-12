---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::public::sign-up"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "author"
      ],
      "when": [
        {
          "entity": "site-settings",
          "fact": "Signups enabled",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py"
    }
  ]
}
---

# Account creation is limited to Author while signups are enabled

Account creation is limited to Author while signups are enabled.
