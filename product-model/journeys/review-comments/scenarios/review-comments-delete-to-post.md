---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author confirms removal of a selected response.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::comment"
        }
      },
      "capability": "delete-comment"
    },
    {
      "text": "The selected response is removed and the actual queue-or-writing destination is used.",
      "kind": "product",
      "entities": [
        {
          "entity": "comment",
          "effect": "removes",
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
      "capability": "delete-comment"
    },
    {
      "text": "No other pending responses remain, so the reviewed writing is selected.",
      "kind": "condition",
      "actor": "author",
      "capability": "delete-comment",
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
      "capability": "delete-comment",
      "contexts": {
        "web": {
          "place": "web::authenticated::comment"
        }
      }
    },
    {
      "text": "The caller requests the selected writing detail.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::post"
        }
      },
      "capability": "read-post"
    },
    {
      "text": "The selected HTML renders title, date and writing with its status and comments disclosure.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Rendered content",
            "Publication date",
            "Publication status",
            "Proper link"
          ]
        },
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [],
          "as": "displayed-responses"
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::post"
        }
      },
      "actor": "author",
      "capability": "read-post"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#CommentDelete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_comment"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PostDetail"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_post"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/static/mcp/posts.js"
    }
  ]
}
---

# Delete to post

## Trigger

Resolve a response and use the product-selected queue or writing destination.

## Outcome

The selected response is removed and the actual queue-or-writing destination is used. The selected HTML renders title, date and writing with its status and comments disclosure.
