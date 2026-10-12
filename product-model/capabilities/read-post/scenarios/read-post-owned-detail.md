---
{
  "kind": "primary",
  "routes": {
    "c-post": "C POST"
  },
  "steps": [
    {
      "text": "The caller requests the selected writing detail.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "c-post": {
          "place": "chatgpt-posts::post"
        }
      }
    },
    {
      "text": "The native Posts view presents selected owned title, date, status and narrowly sanitized HTML, including Draft and Scheduled writing; a public-link action is offered only for published HTTP(S) destinations.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Publication date",
            "Publication status",
            "Canonical link",
            "Rendered content"
          ]
        }
      ],
      "contexts": {
        "c-post": {
          "place": "chatgpt-posts::post"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PostDetail"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_post"
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

# Owned detail

## Trigger

Owned detail: Read post.

## Outcome

The native Posts view presents selected owned title, date, status and narrowly sanitized HTML, including Draft and Scheduled writing; a public-link action is offered only for published HTTP(S) destinations.
