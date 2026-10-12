---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "page",
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

# Page disclosure is limited to Administrator

Page disclosure is limited to Administrator.
