---
{
  "kind": "validation",
  "routes": {
    "w-import-posts": "W IMPORT POSTS"
  },
  "steps": [
    {
      "text": "The author submits UTF-8 text files.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-import-posts": {
          "place": "web::authenticated::import-posts"
        }
      }
    },
    {
      "text": "Failure on the first file leaves no imported entry from this batch.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-import-posts": {
          "place": "web::authenticated::import-posts"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#BlogImport"
    }
  ]
}
---

# Invalid first file

## Trigger

Invalid first file: Import posts.

## Outcome

Failure on the first file leaves no imported entry from this batch.
