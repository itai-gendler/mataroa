---
{
  "kind": "edge",
  "routes": {
    "w-import-posts": "W IMPORT POSTS"
  },
  "steps": [
    {
      "text": "The author submits UTF-8 text files.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-import-posts": {
          "place": "web::authenticated::import-posts"
        }
      }
    },
    {
      "text": "Earlier files persist when a later file fails decoding; no all-batch rollback occurs.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "creates",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Rendered content",
            "Canonical link",
            "Proper link",
            "Created time",
            "Updated time",
            "Publication date",
            "Publication status",
            "Discovery eligibility",
            "Revision fingerprint",
            "Broadcast completion",
            "Newsletter eligibility",
            "Excerpt"
          ]
        }
      ],
      "contexts": {
        "w-import-posts": {
          "place": "web::authenticated::import-posts"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#BlogImport"
    }
  ]
}
---

# Partial import

## Trigger

Partial import: Import posts.

## Outcome

Earlier files persist when a later file fails decoding; no all-batch rollback occurs.
