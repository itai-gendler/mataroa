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
      "text": "Approval becomes true; the web redirects to the pending queue when responses remain, otherwise to the selected writing.",
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

# Approved

## Trigger

Approved: Approve comment.

## Outcome

Approval becomes true; the web redirects to the pending queue when responses remain, otherwise to the selected writing.
