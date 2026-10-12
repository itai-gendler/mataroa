---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-subscription",
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

# Email subscription disclosure is limited to Administrator

Email subscription disclosure is limited to Administrator. The custom reports expose aggregate counts; they do not offer a recipient-address collection.
