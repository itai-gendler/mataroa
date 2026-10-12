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
      "text": "A new selected-Blog email enrollment is immediately active and the Blog is reached, without a confirmation round trip.",
      "kind": "product",
      "entities": [
        {
          "entity": "email-subscription",
          "effect": "creates",
          "to": "Active",
          "facts": [
            "Blog association",
            "Email",
            "Unsubscribe link",
            "Active"
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

# New active

## Trigger

New active: Subscribe by email.

## Outcome

A new selected-Blog email enrollment is immediately active and the Blog is reached, without a confirmation round trip.

## Edge cases

- Invalid email input leaves enrollment unchanged and presents the form error.
