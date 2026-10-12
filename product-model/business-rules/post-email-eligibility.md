---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "creates",
      "contexts": [
        {
          "place": "post-by-email"
        },
        {
          "place": "postmark-webhook"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "contains",
          "entity": "blog"
        },
        {
          "verb": "holds",
          "entity": "account"
        },
        {
          "verb": "has",
          "entity": "author"
        }
      ],
      "when": [
        {
          "entity": "account",
          "fact": "Premium",
          "is": true
        }
      ]
    },
    {
      "related": [
        {
          "verb": "contains",
          "entity": "blog"
        },
        {
          "verb": "holds",
          "entity": "account"
        },
        {
          "verb": "has",
          "entity": "author"
        }
      ],
      "when": [
        {
          "entity": "account",
          "fact": "Grandfathered",
          "is": true
        }
      ]
    },
    {
      "actors": [
        "postmark"
      ],
      "when": [
        {
          "entity": "account",
          "fact": "Premium",
          "is": true
        }
      ]
    },
    {
      "actors": [
        "postmark"
      ],
      "when": [
        {
          "entity": "account",
          "fact": "Grandfathered",
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

# Post creation is limited to the resolved eligible sender or Postmark

Post creation is limited to the resolved eligible sender or Postmark.
