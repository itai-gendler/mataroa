---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::public::post"
        },
        {
          "place": "web::authenticated::post"
        }
      ],
      "facts": [
        "Markdown content"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "reader",
        "author"
      ],
      "when": [
        {
          "fact": "Discovery eligibility",
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

# Post disclosure is limited to a public participant for discovered writing or its owner

Post disclosure is limited to a public participant for discovered writing or its owner. The source guard governs raw Markdown; HTML detail reads its separate rendering.
