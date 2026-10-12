---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post-backup",
      "effect": "creates",
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

# Post backup creation is limited to its owner

Post backup creation is limited to its owner. Automatic capture depends on the browser preference; the save endpoint has no preference eligibility guard.
