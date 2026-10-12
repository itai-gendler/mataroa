---
{
  "kind": "validation",
  "routes": {
    "p": "P",
    "w": "W"
  },
  "steps": [
    {
      "text": "The caller requests the hosted byte address and extension.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p": {
          "place": "web::public"
        },
        "w": {
          "place": "web::authenticated"
        }
      }
    },
    {
      "text": "Missing identity or mismatched extension returns not found.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public"
        },
        "w": {
          "place": "web::authenticated"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#image_raw"
    }
  ]
}
---

# Missing or wrong extension

## Trigger

Missing or wrong extension: Read image file.

## Outcome

Missing identity or mismatched extension returns not found.
