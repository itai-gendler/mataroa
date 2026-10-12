---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "newsletter-history",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::newsletter"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has",
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

# Newsletter history disclosure is limited to its owner

Newsletter history disclosure is limited to its owner.
