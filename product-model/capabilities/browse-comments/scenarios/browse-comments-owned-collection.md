---
{
  "kind": "primary",
  "routes": {
    "w-comments-pending": "W COMMENTS PENDING"
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
        }
      }
    },
    {
      "text": "The pending queue presents the owned unapproved responses with rendered content, supplied identity/email, creation time and review links.",
      "kind": "product",
      "entities": [
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Rendered content",
            "Name",
            "Email",
            "Created time",
            "Link",
            "Author marker",
            "Approval"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "w-comments-pending": {
          "place": "web::authenticated::comments-pending"
        }
      },
      "actor": "author"
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

# Owned collection

## Trigger

Owned collection: Browse comments.

## Outcome

The pending queue presents the owned unapproved responses with rendered content, supplied identity/email, creation time and review links.
