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
      "text": "Field or reserved-name validation retains the submitted process with errors.",
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

# Invalid input

## Trigger

Invalid input: Change blog settings.

## Outcome

Field or reserved-name validation retains the submitted process with errors.
