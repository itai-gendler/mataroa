---
{
  "kind": "validation",
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
      "text": "An address absent from the selected Blog yields not found without deactivation.",
      "kind": "condition",
      "entities": [
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
      }
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

# Address not associated

## Trigger

Address not associated: Unsubscribe by email.

## Outcome

An address absent from the selected Blog yields not found without deactivation.
