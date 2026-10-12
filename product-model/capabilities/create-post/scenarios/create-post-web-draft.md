---
{
  "kind": "primary",
  "routes": {
    "w-new-post": "W NEW POST"
  },
  "steps": [
    {
      "text": "The author submits a title, body and current, future or blank calendar date in the editor.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-new-post": {
          "place": "web::authenticated::new-post"
        }
      }
    },
    {
      "text": "An explicitly blank web date saves undated writing and redirects to its HTML.",
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
        "w-new-post": {
          "place": "web::authenticated::new-post"
        }
      },
      "actor": "author"
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

# Web draft

## Trigger

Web draft: Create post.

## Outcome

An explicitly blank web date saves undated writing and redirects to its HTML.

## Edge cases

- Creation sets creation/update times and leaves broadcast completion absent; classification, links, rendering and revision fingerprint derive from the saved writing and date.
- Calendar dates affect discovery; HTML remains readable by link while undated or future-dated, and no subscriber email is sent inline.
