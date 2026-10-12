---
{
  "kind": "primary",
  "routes": {
    "w-post-backups": "W POST BACKUPS"
  },
  "steps": [
    {
      "text": "The author opens the saved writing collection.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-post-backups": {
          "place": "web::authenticated::post-backups"
        }
      }
    },
    {
      "text": "The author receives owned saved titles and capture times.",
      "kind": "product",
      "entities": [
        {
          "entity": "post-backup",
          "effect": "reads",
          "facts": [
            "Title",
            "Saved time"
          ]
        }
      ],
      "contexts": {
        "w-post-backups": {
          "place": "web::authenticated::post-backups"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#SnapshotList"
    }
  ]
}
---

# Owned collection

## Trigger

Owned collection: Browse post backups.

## Outcome

The author receives owned saved titles and capture times.
