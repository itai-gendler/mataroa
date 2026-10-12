---
{
  "availability": [
    {
      "place": "web::authenticated"
    },
    {
      "place": "blog-api"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PostUpdate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_post"
    }
  ]
}
---

# Edit post

Validated title, cleaned body or permalink changes persist; generated permalinks normalize and resolve owner-scoped collisions.
