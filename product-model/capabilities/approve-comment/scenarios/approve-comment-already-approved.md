---
{
  "kind": "primary",
  "routes": {
    "w-comment": "W COMMENT"
  },
  "steps": [
    {
      "text": "The author submits the approval choice for a selected response.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-comment": {
          "place": "web::authenticated::comment"
        }
      }
    },
    {
      "text": "An already approved response stays approved and the web destination is its writing.",
      "kind": "product",
      "entities": [
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Approval"
          ]
        }
      ],
      "contexts": {
        "w-comment": {
          "place": "web::authenticated::comment"
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

# Already approved

## Trigger

Already approved: Approve comment.

## Outcome

An already approved response stays approved and the web destination is its writing.
