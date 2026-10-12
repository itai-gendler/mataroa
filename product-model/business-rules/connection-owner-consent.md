---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "connected-application",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::connect-application"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "connects",
          "entity": "author"
        }
      ],
      "when": [
        {
          "entity": "account",
          "fact": "Active",
          "is": true
        },
        {
          "entity": "site-settings",
          "fact": "ChatGPT enabled",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/oauth.py"
    }
  ]
}
---

# Connected application creation is limited to its active owner while ChatGPT is enabled

Connected application creation is limited to its active owner while ChatGPT is enabled.
