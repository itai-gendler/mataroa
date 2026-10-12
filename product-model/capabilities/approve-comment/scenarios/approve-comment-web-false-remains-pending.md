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
      "text": "A valid false web approval submission keeps approval false while the success wording still reports approval.",
      "kind": "product",
      "entities": [
        {
          "entity": "comment",
          "effect": "changes",
          "to": "Pending",
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

# Web false remains pending

## Trigger

Web false remains pending: Approve comment.

## Outcome

A valid false web approval submission keeps approval false while the success wording still reports approval.
