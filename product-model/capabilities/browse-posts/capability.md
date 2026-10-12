---
{
  "availability": [
    {
      "place": "blog-api"
    },
    {
      "place": "chatgpt-agent"
    },
    {
      "place": "chatgpt-posts"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_posts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/static/mcp/posts.js"
    }
  ]
}
---

# Browse posts

Browse owned writing through the bearer-key collection, delegated search/filter/pagination or native read-only Posts view. Each contract has its own disclosed facts and failure outcomes.
