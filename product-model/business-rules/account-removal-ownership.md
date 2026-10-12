---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "removes",
      "contexts": [
        {
          "place": "web::authenticated::blog-settings"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
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

# Account removal is limited to its owner

Account removal is limited to its owner.
