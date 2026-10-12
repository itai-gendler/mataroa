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
      "text": "An unknown key presents the failed lookup outcome without removal.",
      "kind": "condition",
      "entities": [],
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

# Unknown key

## Trigger

Unknown key: Unsubscribe by email.

## Outcome

An unknown key presents the failed lookup outcome without removal.
