---
{
  "kind": "edge",
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
      "text": "Owner-review mail failure follows persistence; the pending response remains.",
      "kind": "product",
      "entities": [
        {
          "entity": "comment",
          "effect": "creates",
          "to": "Pending",
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
        "p-post": {
          "place": "web::public::post"
        },
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
      "target": "main/views/general.py#CommentCreate"
    }
  ]
}
---

# Owner mail failed after save

## Trigger

Owner mail failed after save: Leave comment.

## Outcome

Owner-review mail failure follows persistence; the pending response remains.
