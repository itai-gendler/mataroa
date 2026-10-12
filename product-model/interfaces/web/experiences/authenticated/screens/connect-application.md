---
{
  "entities": [
    {
      "entity": "connected-application",
      "shows": [
        "Application name",
        "Consented permissions"
      ],
      "collects": [
        "Consented permissions"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Username"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/oauth.py"
    }
  ]
}
---

# Connect application

Registered client name, requested permissions and current username during owner consent or denial.
