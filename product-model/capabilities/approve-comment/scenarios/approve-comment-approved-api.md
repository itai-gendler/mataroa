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
      "text": "The selected pending response becomes approved.",
      "kind": "product",
      "entities": [
        {
          "entity": "comment",
          "effect": "changes",
          "to": "Approved",
          "facts": [
            "Approval"
          ],
          "from": "Pending"
        }
      ],
      "contexts": {
        "k": {
          "place": "blog-api"
        }
      },
      "actor": "author"
    },
    {
      "text": "The API returns the selected response with raw content, supplied name/email, creation time, permalink, writer marker and approval, plus its parent-writing identity.",
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

# Approved API

## Trigger

Approved: Approve comment.

## Outcome

Approval becomes true and the API returns the serialized owned response, including its raw content and supplied email.
