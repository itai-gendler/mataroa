---
{
  "kind": "primary",
  "routes": {
    "w-post": "W POST",
    "w-comment": "W COMMENT"
  },
  "steps": [
    {
      "text": "The caller requests response disclosure for the selected writing or response identity.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-post": {
          "place": "web::authenticated::post"
        },
        "w-comment": {
          "place": "web::authenticated::comment"
        }
      }
    },
    {
      "text": "The owned pending-review surface presents rendered response content, supplied name/email, time, link and writer-marker and approval flags.",
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
        }
      ],
      "contexts": {
        "w-post": {
          "place": "web::authenticated::post"
        },
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
      "target": "main/views/general.py#PostDetail"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_comment"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    }
  ]
}
---

# Owned contract disclosure

## Trigger

Owned contract disclosure: Read comments.

## Outcome

The owned pending-review surface presents rendered response content, supplied name/email, time, link and writer-marker and approval flags.
