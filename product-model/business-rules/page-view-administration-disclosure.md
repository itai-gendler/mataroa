---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "page-views",
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

# Page views disclosure is limited to Administrator

Page views disclosure is limited to Administrator.
