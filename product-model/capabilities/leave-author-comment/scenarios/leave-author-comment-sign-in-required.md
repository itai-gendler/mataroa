---
{
  "kind": "validation",
  "routes": {
    "w-post": "W POST"
  },
  "steps": [
    {
      "text": "The caller submits an author-marked response.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-post": {
          "place": "web::authenticated::post"
        }
      }
    },
    {
      "text": "A signed-out request follows the configured login continuation without saving a response.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-post": {
          "place": "web::authenticated::post"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#CommentCreateAuthor"
    }
  ]
}
---

# Sign in required

## Trigger

Sign in required: Leave author comment.

## Outcome

A signed-out request follows the configured login continuation without saving a response.
