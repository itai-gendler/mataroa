---
{
  "kind": "primary",
  "routes": {
    "k": "Blog API"
  },
  "steps": [
    {
      "text": "The author submits the approval choice for a selected response.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "The already approved response remains unchanged and the API returns its serialized detail, including raw content and supplied email.",
      "kind": "product",
      "entities": [
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Content",
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
          "facts": [
            "Title",
            "Slug",
            "Canonical link"
          ]
        }
      ],
      "contexts": {
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
      "target": "main/views/general.py#CommentApprove"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_comment_approve"
    }
  ]
}
---

# Already approved API

## Trigger

Already approved: Approve comment.

## Outcome

The already approved response remains unchanged and the API returns its serialized detail, including raw content and supplied email.
