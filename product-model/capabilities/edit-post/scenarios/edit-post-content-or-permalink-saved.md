---
{
  "kind": "primary",
  "routes": {
    "w-post": "W POST",
    "k": "K"
  },
  "steps": [
    {
      "text": "The author supplies changed title, body, permalink or calendar date.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-post": {
          "place": "web::authenticated::post"
        },
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "Validated title, cleaned body or permalink changes persist; generated permalinks normalize and resolve owner-scoped collisions.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Updated time",
            "Rendered content",
            "Canonical link",
            "Proper link",
            "Revision fingerprint",
            "Excerpt"
          ]
        }
      ],
      "contexts": {
        "w-post": {
          "place": "web::authenticated::post"
        },
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
      "target": "main/views/general.py#PostUpdate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_post"
    }
  ]
}
---

# Content or permalink saved

## Trigger

Content or permalink saved: Edit post.

## Outcome

Validated title, cleaned body or permalink changes persist; generated permalinks normalize and resolve owner-scoped collisions.

## Edge cases

- API fields absent from the request remain unchanged; supplied changes preserve existing broadcast completion. The web generation suffix requests normalized permalink generation.
