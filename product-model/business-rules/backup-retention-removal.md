---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post-backup",
      "effect": "removes",
      "contexts": [
        {
          "place": "web::authenticated::new-post"
        },
        {
          "place": "web::authenticated::post"
        }
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

# Post backup removal is limited to its owner

Post backup removal is limited to its owner.
