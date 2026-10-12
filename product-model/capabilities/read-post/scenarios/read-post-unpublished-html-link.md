---
{
  "kind": "primary",
  "routes": {
    "p-post": "P POST",
    "w-post": "W POST"
  },
  "steps": [
    {
      "text": "The caller requests the selected writing detail.",
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
      "text": "An undated or future-dated HTML link still renders with the unpublished status notice.",
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

# Unpublished html link

## Trigger

Unpublished html link: Read post.

## Outcome

An undated or future-dated HTML link still renders with the unpublished status notice.

## Edge cases

- Link readability is distinct from feed/index visibility and from unpublished raw-source refusal.
