---
{
  "kind": "primary",
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
      "text": "The valid ordinary response is saved pending and an owner-review email is attempted before returning to the selected writing.",
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

# Pending and owner mail attempt

## Trigger

Pending and owner mail attempt: Leave comment.

## Outcome

The valid ordinary response is saved pending and an owner-review email is attempted before returning to the selected writing.

## Edge cases

- Invalid response fields retain form errors and refresh the signed timing input; no response is saved.
