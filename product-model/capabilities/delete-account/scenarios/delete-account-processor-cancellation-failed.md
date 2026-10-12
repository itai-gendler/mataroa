---
{
  "kind": "edge",
  "routes": {
    "w-blog-settings": "W BLOG SETTINGS"
  },
  "steps": [
    {
      "text": "The author confirms permanent removal of their identity and owned writing.",
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
      "text": "A caught processor cancellation error produces service failure and preserves the identity and owned writing.",
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
      "target": "main/views/general.py#UserDelete"
    }
  ]
}
---

# Processor cancellation failed

## Trigger

Processor cancellation failed: Delete account.

## Outcome

A caught processor cancellation error produces service failure and preserves the identity and owned writing.
