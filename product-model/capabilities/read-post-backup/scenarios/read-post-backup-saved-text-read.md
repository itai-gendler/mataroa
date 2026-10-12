---
{
  "kind": "primary",
  "routes": {
    "w-post-backup": "W POST BACKUP"
  },
  "steps": [
    {
      "text": "The author selects a saved writing capture.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-post-backup": {
          "place": "web::authenticated::post-backup"
        }
      }
    },
    {
      "text": "The selected saved title, text and time are presented without a restore operation.",
      "kind": "product",
      "entities": [
        {
          "entity": "post-backup",
          "effect": "reads",
          "facts": [
            "Title",
            "Content",
            "Saved time"
          ]
        }
      ],
      "contexts": {
        "w-post-backup": {
          "place": "web::authenticated::post-backup"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#SnapshotDetail"
    }
  ]
}
---

# Saved text read

## Trigger

Saved text read: Read post backup.

## Outcome

The selected saved title, text and time are presented without a restore operation.
