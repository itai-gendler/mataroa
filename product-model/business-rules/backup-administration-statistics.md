---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post-backup",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::restricted::moderation"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "administrator"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/moderation.py"
    }
  ]
}
---

# Post backup disclosure is limited to Administrator

Post backup disclosure is limited to Administrator.
