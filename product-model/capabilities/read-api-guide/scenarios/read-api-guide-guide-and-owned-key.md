---
{
  "kind": "primary",
  "routes": {
    "w-api": "W API"
  },
  "steps": [
    {
      "text": "The caller opens the shipped API guide.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-api": {
          "place": "web::authenticated::api"
        }
      }
    },
    {
      "text": "The author guide presents the current owned key and reset outcome.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "API key"
          ]
        }
      ],
      "contexts": {
        "w-api": {
          "place": "web::authenticated::api"
        }
      },
      "actor": "author"
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

# Guide and owned key

## Trigger

Guide and owned key: Read API guide.

## Outcome

The author guide presents the current owned key and reset outcome.
