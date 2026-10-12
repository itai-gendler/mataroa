---
{
  "kind": "primary",
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
      "text": "On the first day, enabled identities receive a generated Markdown ZIP by email with a keyed stop link; an export receipt follows the send call.",
      "kind": "product",
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

# First day enabled mail

## Trigger

First day enabled mail: Mail blog export.

## Outcome

On the first day, enabled identities receive a generated Markdown ZIP by email with a keyed stop link; an export receipt follows the send call.
