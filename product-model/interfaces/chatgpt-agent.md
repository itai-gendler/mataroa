---
{
  "type": "agent",
  "actors": [
    "ai-agent"
  ],
  "entryPoints": [
    {
      "agent": "/mcp"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/urls.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/urls.py"
    }
  ]
}
---

# ChatGPT agent

Optional OAuth connection and fixed delegated MCP contract when ChatGPT is enabled.
