---
{
  "kind": "primary",
  "routes": {
    "a": "A"
  },
  "steps": [
    {
      "text": "The caller confirms removal of the selected writing, with a fingerprint on the delegated contract.",
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
      "text": "Following the shipped target review instructions, matching delegated deletion removes the selected revision and dependents.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "removes"
        },
        {
          "entity": "comment",
          "effect": "removes",
          "with": "post",
          "from": "Approved",
          "as": "approved-responses"
        },
        {
          "entity": "comment",
          "effect": "removes",
          "with": "post",
          "from": "Pending",
          "as": "pending-responses"
        },
        {
          "entity": "post-views",
          "effect": "removes",
          "with": "post"
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
      "target": "main/views/general.py#PostDelete"
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
    }
  ]
}
---

# Reviewed agent deletion

## Trigger

Reviewed agent deletion: Delete post.

## Outcome

Following the shipped target review instructions, matching delegated deletion removes the selected revision and dependents.
