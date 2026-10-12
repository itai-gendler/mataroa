---
{
  "kind": "validation",
  "routes": {
    "w-comment": "W COMMENT",
    "k": "K"
  },
  "steps": [
    {
      "text": "The author confirms removal of a selected response.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-comment": {
          "place": "web::authenticated::comment"
        },
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "An unowned response is refused without removal.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-comment": {
          "place": "web::authenticated::comment"
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
      "target": "main/views/general.py#CommentDelete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_comment"
    }
  ]
}
---

# Other owner refused

## Trigger

Other owner refused: Delete comment.

## Outcome

An unowned response is refused without removal.
