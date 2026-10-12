---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "reads",
      "contexts": [
        {
          "place": "chatgpt-agent"
        }
      ],
      "facts": [
        "Email"
      ]
    }
  ],
  "permits": [],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py"
    }
  ]
}
---

# Comment disclosure is limited to nobody

Comment disclosure is limited to nobody.
