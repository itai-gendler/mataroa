---
{
  "kind": "primary",
  "routes": {
    "w-new-post": "W NEW POST",
    "w-post": "W POST"
  },
  "steps": [
    {
      "text": "The browser submits the current title and text capture.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-new-post": {
          "place": "web::authenticated::new-post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        }
      }
    },
    {
      "text": "A title/body capture is saved with its save time; an empty title receives Untitled, and no live writing association is kept.",
      "kind": "product",
      "entities": [
        {
          "entity": "post-backup",
          "effect": "creates",
          "facts": [
            "Title",
            "Content",
            "Saved time"
          ]
        }
      ],
      "contexts": {
        "w-new-post": {
          "place": "web::authenticated::new-post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#SnapshotCreate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/templates/assets/save-snapshot.js"
    }
  ]
}
---

# Capture saved

## Trigger

Capture saved: Save post backup.

## Outcome

A title/body capture is saved with its save time; an empty title receives Untitled, and no live writing association is kept.
