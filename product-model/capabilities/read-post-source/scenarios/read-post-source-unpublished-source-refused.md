---
{
  "kind": "validation",
  "routes": {
    "p-post": "P POST",
    "w-post": "W POST"
  },
  "steps": [
    {
      "text": "The caller requests raw Markdown at the selected writing address.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-post": {
          "place": "web::public::post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        }
      }
    },
    {
      "text": "An unpublished raw-source request outside the own-target contract returns not found.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p-post": {
          "place": "web::public::post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#post_raw"
    }
  ]
}
---

# Unpublished source refused

## Trigger

Unpublished source refused: Read post source.

## Outcome

An unpublished raw-source request outside the own-target contract returns not found.
