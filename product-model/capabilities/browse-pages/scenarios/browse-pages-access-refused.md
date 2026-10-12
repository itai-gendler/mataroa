---
{
  "kind": "validation",
  "routes": {
    "w-pages": "W PAGES",
    "k": "K"
  },
  "steps": [
    {
      "text": "The caller requests the owned static-writing collection.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-pages": {
          "place": "web::authenticated::pages"
        },
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "Missing bearer or delegated read scope prevents retrieval.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-pages": {
          "place": "web::authenticated::pages"
        },
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
      "target": "main/views/general.py#PageList"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_pages"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    }
  ]
}
---

# Access refused

## Trigger

Access refused: Browse pages.

## Outcome

Missing bearer or delegated read scope prevents retrieval.
