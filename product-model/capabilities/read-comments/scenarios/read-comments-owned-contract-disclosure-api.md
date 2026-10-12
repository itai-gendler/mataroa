---
{
  "kind": "primary",
  "routes": {
    "k": "K"
  },
  "steps": [
    {
      "text": "The caller requests response disclosure for the selected writing or response identity.",
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
      "text": "The bearer-key detail returns raw content, identity, email, time, link, author marker and approval for the selected owned response.",
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

The bearer-key detail returns raw content, identity, email, time, link, author marker and approval for the selected owned response.
