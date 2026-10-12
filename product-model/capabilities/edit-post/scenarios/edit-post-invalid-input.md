---
{
  "kind": "validation",
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
      "text": "Invalid fields or conflicting permalink leave the requested edit unsaved.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-post": {
          "place": "web::authenticated::post"
        },
        "k": {
          "place": "blog-api"
        }
      }
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

# Invalid input

## Trigger

Invalid input: Edit post.

## Outcome

Invalid fields or conflicting permalink leave the requested edit unsaved.
