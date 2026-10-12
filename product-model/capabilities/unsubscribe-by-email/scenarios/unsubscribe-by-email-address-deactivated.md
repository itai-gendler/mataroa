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
      "text": "A matching Blog/address enrollment becomes inactive and the Blog is reached.",
      "kind": "product",
      "entities": [
        {
          "entity": "email-subscription",
          "effect": "changes",
          "to": "Inactive",
          "facts": [
            "Active"
          ],
          "from": "Active"
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

# Address deactivated

## Trigger

Address deactivated: Unsubscribe by email.

## Outcome

A matching Blog/address enrollment becomes inactive and the Blog is reached.
