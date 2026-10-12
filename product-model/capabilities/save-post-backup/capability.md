---
{
  "availability": [
    {
      "place": "web::authenticated"
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
  ],
  "domain": "post-backups"
}
---

# Save Post Backup

A title/body capture is saved with its save time; an empty title receives Untitled, and no live writing association is kept.
