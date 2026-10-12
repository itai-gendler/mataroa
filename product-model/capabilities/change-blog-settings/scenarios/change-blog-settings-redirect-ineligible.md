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
      "text": "The retirement field is excluded for an ineligible identity and cannot change that destination through this form.",
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

# Redirect ineligible

## Trigger

Redirect ineligible: Change blog settings.

## Outcome

The retirement field is excluded for an ineligible identity and cannot change that destination through this form.
