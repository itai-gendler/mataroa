---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "blog",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::blog-settings"
        }
      ],
      "facts": [
        "Retirement destination"
      ]
    }
  ],
  "permits": [
    {
      "related": [
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
      "related": [
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
          "fact": "Redirect grandfathered",
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

# Blog modification is limited to its eligible owner

Blog modification is limited to its eligible owner.
