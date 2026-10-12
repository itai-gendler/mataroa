---
{
  "kind": "primary",
  "routes": {
    "k": "K",
    "c-posts": "C POSTS"
  },
  "steps": [
    {
      "text": "The caller requests an owned collection, search, status or pagination selection.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "k": {
          "place": "blog-api"
        },
        "c-posts": {
          "place": "chatgpt-posts::posts"
        }
      }
    },
    {
      "text": "A valid search or selection with no matches returns an empty collection.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Publication date",
            "Publication status",
            "Canonical link",
            "Proper link"
          ]
        }
      ],
      "contexts": {
        "k": {
          "place": "blog-api"
        },
        "c-posts": {
          "place": "chatgpt-posts::posts"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_posts"
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

# Empty result

## Trigger

Empty result: Browse posts.

## Outcome

A valid search or selection with no matches returns an empty collection.

## Edge cases

- API collection/detail also returns Markdown content and canonical link. Native collection is a summary; native detail presents normalized rendered content and a public link only when Published.
