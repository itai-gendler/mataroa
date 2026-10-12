---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "connected-application",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::connect-application"
        },
        {
          "place": "chatgpt-agent"
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
      ]
    },
    {
      "related": [
        {
          "verb": "connects",
          "entity": "author"
        },
        {
          "verb": "connects",
          "entity": "connected-application"
        },
        {
          "verb": "delegates to",
          "entity": "ai-agent"
        }
      ],
      "when": [
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

# Connected application disclosure is limited to its owner or bound AI agent

Connected application disclosure is limited to its owner or bound AI agent. Owner and bound-caller reads select the same consent family; a different connection sharing its owner is not substituted.

The bound-caller path goes through the consenting person and returns to the same credential-selected family before reaching its caller.
