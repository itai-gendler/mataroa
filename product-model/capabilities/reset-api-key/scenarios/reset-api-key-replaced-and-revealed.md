---
{
  "kind": "primary",
  "routes": {
    "w-api": "W API"
  },
  "steps": [
    {
      "text": "The author requests a replacement bearer key.",
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
      "text": "A new random key replaces the current key and is revealed; the replaced bearer no longer resolves.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
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
      "target": "main/views/api.py#APIKeyReset"
    }
  ]
}
---

# Replaced and revealed

## Trigger

Replaced and revealed: Reset API key.

## Outcome

A new random key replaces the current key and is revealed; the replaced bearer no longer resolves.
