---
{
  "availability": [
    {
      "place": "web::authenticated"
    },
    {
      "place": "blog-api"
    },
    {
      "place": "chatgpt-agent"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#CommentPending"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_comments"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    }
  ],
  "domain": "comments-pending"
}
---

# Browse comments

The web queue returns owned pending responses; API offers all/post/pending selections and delegated collection uses its narrower read contract.
