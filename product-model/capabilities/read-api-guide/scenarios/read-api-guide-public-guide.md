---
{
  "kind": "primary",
  "routes": {
    "p-api": "P API"
  },
  "steps": [
    {
      "text": "The caller opens the shipped API guide.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-api": {
          "place": "web::public::api"
        }
      }
    },
    {
      "text": "The public guide explains the shipped API contract without a private key.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p-api": {
          "place": "web::public::api"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_docs"
    }
  ]
}
---

# Public guide

## Trigger

Public guide: Read API guide.

## Outcome

The public guide explains the shipped API contract without a private key.
