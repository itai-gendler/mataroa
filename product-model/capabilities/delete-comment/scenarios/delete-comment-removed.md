---
{
  "kind": "primary",
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
      "text": "The selected response is removed and the actual queue-or-writing destination is used.",
      "kind": "product",
      "entities": [
        {
          "entity": "comment",
          "effect": "removes",
          "from": "Pending"
        }
      ],
      "contexts": {
        "w-comment": {
          "place": "web::authenticated::comment"
        },
        "k": {
          "place": "blog-api"
        }
      },
      "actor": "author"
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

# Removed

## Trigger

Removed: Delete comment.

## Outcome

The selected response is removed and the actual queue-or-writing destination is used.

## Edge cases

- The selected response can also already be Approved; that state is removed with the same destination-selection behavior.
