---
{
  "kind": "primary",
  "routes": {
    "p-email-subscription": "P EMAIL SUBSCRIPTION",
    "w-email-subscription": "W EMAIL SUBSCRIPTION"
  },
  "steps": [
    {
      "text": "The participant supplies an email address for enrollment.",
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
      "text": "A retained inactive address is reactivated and the Blog is reached.",
      "kind": "product",
      "entities": [
        {
          "entity": "email-subscription",
          "effect": "changes",
          "to": "Active",
          "facts": [
            "Active"
          ],
          "from": "Inactive"
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
      "target": "main/views/general.py#Notification"
    }
  ]
}
---

# Reactivated

## Trigger

Reactivated: Subscribe by email.

## Outcome

A retained inactive address is reactivated and the Blog is reached.
