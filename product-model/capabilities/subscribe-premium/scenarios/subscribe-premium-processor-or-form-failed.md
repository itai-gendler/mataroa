---
{
  "kind": "edge",
  "routes": {
    "w-subscribe-premium": "W SUBSCRIBE PREMIUM"
  },
  "steps": [
    {
      "text": "The author begins initial payment or saved-method resubscription and follows confirmation.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-subscribe-premium": {
          "place": "web::authenticated::subscribe-premium"
        }
      }
    },
    {
      "text": "Processor, missing confirmation secret or invalid form outcomes prevent completed subscription; existing customer/subscription preparation can remain.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-subscribe-premium": {
          "place": "web::authenticated::subscribe-premium"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#BillingSubscribe"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#BillingResubscribe"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_welcome"
    }
  ]
}
---

# Processor or form failed

## Trigger

Processor or form failed: Subscribe premium.

## Outcome

Processor, missing confirmation secret or invalid form outcomes prevent completed subscription; existing customer/subscription preparation can remain.
