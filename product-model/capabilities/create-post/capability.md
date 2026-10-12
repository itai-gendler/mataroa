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
      "place": "post-by-email"
    },
    {
      "place": "postmark-webhook"
    },
    {
      "place": "chatgpt-agent"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PostCreate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_posts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#postmark_webhook"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    }
  ]
}
---

# Create post

Save writing through the browser, owned API, subject/text email or delegated draft contract. Supplied dates and defaults differ by contract; creation itself does not send subscriber mail.
