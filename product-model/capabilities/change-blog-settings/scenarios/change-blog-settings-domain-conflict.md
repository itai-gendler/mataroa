---
{
  "kind": "validation",
  "routes": {
    "w-blog-settings": "W BLOG SETTINGS"
  },
  "steps": [
    {
      "text": "The author supplies profile and exposed writing-destination preferences.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-blog-settings": {
          "place": "web::authenticated::blog-settings"
        }
      }
    },
    {
      "text": "A custom domain already used by another identity is rejected without saving that change.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-blog-settings": {
          "place": "web::authenticated::blog-settings"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#UserUpdate"
    }
  ]
}
---

# Domain conflict

## Trigger

Domain conflict: Change blog settings.

## Outcome

A custom domain already used by another identity is rejected without saving that change.
