---
{
  "kind": "primary",
  "routes": {
    "w-post": "W POST",
    "k": "K"
  },
  "steps": [
    {
      "text": "The caller confirms removal of the selected writing, with a fingerprint on the delegated contract.",
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
      "text": "The selected owned writing and dependent responses/visits are removed; nullable accounting links remain. Web redirects to the remaining Blog.",
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
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": []
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

# Ordinary owner deletion

## Trigger

Ordinary owner deletion: Delete post.

## Outcome

The selected owned writing and dependent responses/visits are removed; nullable accounting links remain. Web redirects to the remaining Blog.
