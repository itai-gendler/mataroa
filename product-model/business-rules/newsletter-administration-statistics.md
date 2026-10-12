---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "newsletter-history",
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

# Newsletter history disclosure is limited to Administrator

Newsletter history disclosure is limited to Administrator.
