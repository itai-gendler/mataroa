---
{
  "kind": "primary",
  "routes": {
    "p-post": "P POST",
    "w-post": "W POST"
  },
  "steps": [
    {
      "text": "The caller requests response disclosure for the selected writing or response identity.",
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
      "text": "Approved responses disclose public content, name, time, link and author marker without email.",
      "kind": "product",
      "entities": [
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Rendered content",
            "Name",
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

# Approved public disclosure

## Trigger

Approved public disclosure: Read comments.

## Outcome

Approved responses disclose public content, name, time, link and author marker without email.
