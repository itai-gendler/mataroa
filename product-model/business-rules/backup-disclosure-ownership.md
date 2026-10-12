---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post-backup",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::post-backups"
        },
        {
          "place": "web::authenticated::post-backup"
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

# Post backup disclosure is limited to its owner

Post backup disclosure is limited to its owner.
