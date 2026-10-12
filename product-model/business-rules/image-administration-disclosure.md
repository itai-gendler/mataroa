---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "image",
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

# Image disclosure is limited to Administrator

Image disclosure is limited to Administrator.
