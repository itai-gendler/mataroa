---
{
  "kind": "validation",
  "routes": {
    "k": "K"
  },
  "steps": [
    {
      "text": "The caller requests selected static-writing detail.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "Missing or unowned selected detail is refused.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "k": {
          "place": "blog-api"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PageDetail"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_page"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    }
  ]
}
---

# Missing or unowned

## Trigger

Missing or unowned: Read page.

## Outcome

Missing or unowned selected detail is refused.
