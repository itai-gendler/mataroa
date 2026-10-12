---
{
  "kind": "validation",
  "routes": {
    "w-comments-pending": "W COMMENTS PENDING",
    "k": "K"
  },
  "steps": [
    {
      "text": "The caller requests the response queue or a supported owner-bound response selection.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-comments-pending": {
          "place": "web::authenticated::comments-pending"
        },
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "Missing contract credentials or read scope prevents collection disclosure.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-comments-pending": {
          "place": "web::authenticated::comments-pending"
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
  ]
}
---

# Access refused

## Trigger

Access refused: Browse comments.

## Outcome

Missing contract credentials or read scope prevents collection disclosure.
