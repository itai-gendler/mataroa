---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author submits the approval choice for a selected response.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::comment"
        }
      },
      "capability": "approve-comment"
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
          "from": "Pending",
          "as": "selected-response"
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::comment"
        }
      },
      "actor": "author",
      "capability": "approve-comment"
    },
    {
      "text": "Other pending responses remain, so the pending queue is selected.",
      "kind": "condition",
      "actor": "author",
      "capability": "approve-comment",
      "entities": [
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Approval"
          ],
          "as": "remaining-responses"
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::comment"
        }
      }
    },
    {
      "text": "The remaining pending-response count selects the queue redirect or the reviewed writing destination.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "approve-comment",
      "contexts": {
        "web": {
          "place": "web::authenticated::comment"
        }
      }
    },
    {
      "text": "The caller requests the response queue or a supported owner-bound response selection.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::comments-pending"
        }
      },
      "capability": "browse-comments"
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
          ],
          "as": "remaining-responses"
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::comments-pending"
        }
      },
      "actor": "author",
      "capability": "browse-comments"
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
    },
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

# Approve to queue

## Trigger

Resolve a response and use the product-selected queue or writing destination.

## Outcome

The selected response becomes approved and the actual web review destination is reached. The pending queue presents the owned unapproved responses with rendered content, supplied identity/email, creation time and review links.
