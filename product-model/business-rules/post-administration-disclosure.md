---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::restricted"
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

# Post disclosure is limited to Administrator

Post disclosure is limited to Administrator.
