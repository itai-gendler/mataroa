---
{
  "kind": "validation",
  "routes": {
    "p-post": "P POST",
    "w-post": "W POST"
  },
  "steps": [
    {
      "text": "The caller submits response text, optional identity fields and spam-control input.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-post": {
          "place": "web::public::post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        }
      }
    },
    {
      "text": "Disabled comments prevent ordinary submission.",
      "kind": "condition",
      "entities": [
        {
          "entity": "comment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "p-post": {
          "place": "web::public::post"
        },
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
      "target": "main/views/general.py#CommentCreate"
    }
  ]
}
---

# Comments disabled

## Trigger

Comments disabled: Leave comment.

## Outcome

Disabled comments prevent ordinary submission.
