---
{
  "kind": "validation",
  "routes": {
    "p-post": "P POST",
    "w-post": "W POST",
    "k": "K",
    "c-post": "C POST"
  },
  "steps": [
    {
      "text": "The caller requests the selected writing detail.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-post": {
          "place": "web::public::post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        },
        "k": {
          "place": "blog-api"
        },
        "c-post": {
          "place": "chatgpt-posts::post"
        }
      }
    },
    {
      "text": "A missing target, or an unowned target in an owner-bound contract, does not disclose the selected detail.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p-post": {
          "place": "web::public::post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        },
        "k": {
          "place": "blog-api"
        },
        "c-post": {
          "place": "chatgpt-posts::post"
        }
      }
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

# Missing or unowned

## Trigger

Missing or unowned: Read post.

## Outcome

A missing target, or an unowned target in an owner-bound contract, does not disclose the selected detail.

## Edge cases

- API collection/detail also returns Markdown content and canonical link. Native collection is a summary; native detail presents normalized rendered content and a public link only when Published.
