---
{
  "kind": "primary",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The caller requests the response queue or a supported owner-bound response selection.",
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
      "text": "The delegated collection returns owned responses with raw content, name, creation time, writer-marker and approval flags and parent-writing links; all, selected-parent and pending-only selections are paginated and email is omitted.",
      "kind": "product",
      "entities": [
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Content",
            "Name",
            "Created time",
            "Link",
            "Author marker",
            "Approval"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": []
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

# Owned collection

## Trigger

Owned collection: Browse comments.

## Outcome

The delegated collection returns owned responses with raw content, name, creation time, writer-marker and approval flags and parent-writing links; all, selected-parent and pending-only selections are paginated and email is omitted.
