---
{
  "kind": "primary",
  "routes": {
    "p": "P",
    "w": "W"
  },
  "steps": [
    {
      "text": "The caller follows the keyed export-stop address.",
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
      "text": "The globally key-selected preference is disabled and its stop key rotates before the outcome renders.",
      "kind": "product",
      "entities": [
        {
          "entity": "blog",
          "effect": "changes",
          "facts": [
            "Mail export enabled",
            "Export-stop link"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Email"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public"
        },
        "w": {
          "place": "web::authenticated"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/export.py#export_unsubscribe_key"
    }
  ]
}
---

# Disabled and key rotated

## Trigger

Disabled and key rotated: Stop mail exports.

## Outcome

The globally key-selected preference is disabled and its stop key rotates before the outcome renders.

## Edge cases

- A request without the required Blog rendering context can fail after the preference was disabled and key rotated.
