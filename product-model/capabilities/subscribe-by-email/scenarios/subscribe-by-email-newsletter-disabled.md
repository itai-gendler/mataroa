---
{
  "kind": "validation",
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
      "text": "With newsletter disabled the process redirects to the Blog without new enrollment.",
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
      "target": "main/views/general.py#Notification"
    }
  ]
}
---

# Newsletter disabled

## Trigger

Newsletter disabled: Subscribe by email.

## Outcome

With newsletter disabled the process redirects to the Blog without new enrollment.
