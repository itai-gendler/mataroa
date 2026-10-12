---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::newsletter"
        }
      ],
      "facts": [
        "Title",
        "Markdown content",
        "Rendered content",
        "Publication date",
        "Proper link"
      ]
    }
  ],
  "permits": [
    {
      "unattended": true,
      "when": [
        {
          "fact": "Newsletter eligibility",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/management/commands/processnotifications.py"
    }
  ]
}
---

# Post disclosure is limited to the eligible unattended dispatch

Post disclosure is limited to the eligible unattended dispatch.
