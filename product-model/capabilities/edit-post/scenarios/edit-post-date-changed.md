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
      "text": "A valid calendar-date replacement persists without clearing broadcast completion.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Publication date",
            "Updated time",
            "Revision fingerprint",
            "Publication status",
            "Discovery eligibility",
            "Newsletter eligibility"
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

# Date changed

## Trigger

Date changed: Edit post.

## Outcome

A valid calendar-date replacement persists without clearing broadcast completion.
