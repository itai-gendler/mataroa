---
{
  "kind": "primary",
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
      "text": "The exposed owner response saves an approved author-marked response with the caller username, then returns to the selected writing.",
      "kind": "product",
      "entities": [
        {
          "entity": "comment",
          "effect": "creates",
          "to": "Approved",
          "facts": [
            "Content",
            "Rendered content",
            "Name",
            "Email",
            "Created time",
            "Link",
            "Author marker",
            "Approval"
          ]
        }
      ],
      "contexts": {
        "w-post": {
          "place": "web::authenticated::post"
        }
      },
      "actor": "author"
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

# Approved author response

## Trigger

Approved author response: Leave author comment.

## Outcome

The exposed owner response saves an approved author-marked response with the caller username, then returns to the selected writing.
