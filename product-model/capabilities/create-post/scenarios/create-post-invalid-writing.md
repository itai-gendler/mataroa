---
{
  "kind": "validation",
  "routes": {
    "w-new-post": "W NEW POST",
    "k": "K"
  },
  "steps": [
    {
      "text": "The author submits title, body and calendar-date input through the editor or current-key contract.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-new-post": {
          "place": "web::authenticated::new-post"
        },
        "k": {
          "place": "blog-api"
        }
      }
    },
    {
      "text": "Invalid title, date or content produces the contract-specific validation result without the requested creation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-new-post": {
          "place": "web::authenticated::new-post"
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
      "target": "main/views/general.py#PostCreate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_posts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#postmark_webhook"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    }
  ]
}
---

# Invalid writing

## Trigger

Invalid writing: Create post.

## Outcome

Invalid title, date or content produces the contract-specific validation result without the requested creation.
