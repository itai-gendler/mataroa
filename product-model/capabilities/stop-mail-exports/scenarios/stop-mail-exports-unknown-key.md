---
{
  "kind": "validation",
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
      "text": "With a resolved host, an unknown stop key renders the unsuccessful unsubscribe outcome without changing a preference or key.",
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
      "target": "main/views/export.py#export_unsubscribe_key"
    }
  ]
}
---

# Unknown key

## Trigger

Unknown key: Stop mail exports.

## Outcome

With a resolved host, an unknown stop key renders the unsuccessful unsubscribe outcome without changing a preference or key.

## Edge cases

- Without resolved blog context, rendering can fail; no preference was changed for an unknown key.
