---
{
  "kind": "edge",
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
      "text": "After capture, older entries beyond the newest 250 are removed.",
      "kind": "product",
      "entities": [
        {
          "entity": "post-backup",
          "effect": "creates",
          "facts": [
            "Title",
            "Content",
            "Saved time"
          ],
          "as": "new-capture"
        },
        {
          "entity": "post-backup",
          "effect": "removes",
          "as": "old-capture"
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

# Older captures pruned

## Trigger

Older captures pruned: Save post backup.

## Outcome

After capture, older entries beyond the newest 250 are removed.
