---
{
  "kind": "validation",
  "routes": {
    "w-post": "W POST",
    "k": "K"
  },
  "steps": [
    {
      "text": "The caller confirms removal of the selected writing, with a fingerprint on the delegated contract.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-post": {
          "place": "web::authenticated::post"
        },
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "A missing or unowned target is refused without removal.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-post": {
          "place": "web::authenticated::post"
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
      "target": "main/views/general.py#PostDelete"
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
    }
  ]
}
---

# Missing or unowned

## Trigger

Missing or unowned: Delete post.

## Outcome

A missing or unowned target is refused without removal.
