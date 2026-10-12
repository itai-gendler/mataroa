---
{
  "kind": "edge",
  "routes": {
    "w-blog-settings": "W BLOG SETTINGS"
  },
  "steps": [
    {
      "text": "The scheduled real processing run starts.",
      "kind": "condition",
      "entities": [],
      "unattended": true,
      "contexts": {
        "w-blog-settings": {
          "place": "web::authenticated::blog-settings"
        }
      }
    },
    {
      "text": "An uncaught generation or mail error aborts the run, without a deduplication or retry guarantee.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Email",
            "Username"
          ]
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": [
            "Mail export enabled",
            "Title",
            "Export-stop link"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Publication date",
            "Created time"
          ]
        },
        {
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Markdown content"
          ]
        }
      ],
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
      "target": "main/management/commands/mailexports.py#Command.handle"
    }
  ]
}
---

# Send failure aborts run

## Trigger

Send failure aborts run: Mail blog export.

## Outcome

An uncaught generation or mail error aborts the run, without a deduplication or retry guarantee.
