---
{
  "kind": "primary",
  "routes": {
    "p-email-subscription": "P EMAIL SUBSCRIPTION",
    "w-email-subscription": "W EMAIL SUBSCRIPTION"
  },
  "steps": [
    {
      "text": "The participant supplies an enrolled address or follows the keyed removal address.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-email-subscription": {
          "place": "web::public::email-subscription"
        },
        "w-email-subscription": {
          "place": "web::authenticated::email-subscription"
        }
      }
    },
    {
      "text": "After blog-host resolution the global key selects and deletes its enrollment; the outcome presents the selected address.",
      "kind": "product",
      "entities": [
        {
          "entity": "email-subscription",
          "effect": "reads",
          "facts": [
            "Email"
          ]
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "p-email-subscription": {
          "place": "web::public::email-subscription"
        },
        "w-email-subscription": {
          "place": "web::authenticated::email-subscription"
        }
      },
      "actor": "author"
    },
    {
      "text": "The global key-selected active enrollment is removed.",
      "kind": "product",
      "entities": [
        {
          "entity": "email-subscription",
          "effect": "removes",
          "from": "Active"
        }
      ],
      "contexts": {
        "p-email-subscription": {
          "place": "web::public::email-subscription"
        },
        "w-email-subscription": {
          "place": "web::authenticated::email-subscription"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#NotificationUnsubscribe"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#notification_unsubscribe_key"
    }
  ]
}
---

# Key deleted

## Trigger

A participant follows the globally keyed removal link for an active enrollment on a resolved Blog host.

## Outcome

After blog-host resolution the global key selects and deletes its enrollment; the outcome presents the selected address.

## Edge cases

- An Inactive keyed enrollment is also removed; keyed removal is global after requiring a Blog host, whereas address deactivation is scoped to the selected Blog.
