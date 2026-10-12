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
      "text": "Outside the first day no export processing occurs.",
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
      "target": "main/management/commands/mailexports.py#Command.handle"
    }
  ]
}
---

# Not first day

## Trigger

Not first day: Mail blog export.

## Outcome

Outside the first day no export processing occurs.
