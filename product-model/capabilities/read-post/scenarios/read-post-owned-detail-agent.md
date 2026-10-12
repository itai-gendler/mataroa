---
{
  "kind": "primary",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The caller requests the selected writing detail.",
      "kind": "actor",
      "entities": [],
      "actor": "ai-agent",
      "contexts": {
        "a": {
          "place": "chatgpt-agent"
        }
      }
    },
    {
      "text": "The delegated detail returns the selected owned title, slug, source, date, canonical link, revision fingerprint and narrowly sanitized HTML; embeds, styles, IDs and classes are omitted from that rendering.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Rendered content",
            "Publication date",
            "Canonical link",
            "Revision fingerprint"
          ]
        }
      ],
      "contexts": {
        "a": {
          "place": "chatgpt-agent"
        }
      },
      "actor": "ai-agent"
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

# Owned detail

## Trigger

Owned detail: Read post.

## Outcome

The delegated detail returns the selected owned title, slug, source, date, canonical link, revision fingerprint and narrowly sanitized HTML; embeds, styles, IDs and classes are omitted from that rendering.
