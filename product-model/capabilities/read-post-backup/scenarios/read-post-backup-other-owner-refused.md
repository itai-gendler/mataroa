---
{
  "kind": "validation",
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
      "text": "An unowned capture is refused without disclosure.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-post-backup": {
          "place": "web::authenticated::post-backup"
        }
      }
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

# Other owner refused

## Trigger

Other owner refused: Read post backup.

## Outcome

An unowned capture is refused without disclosure.
