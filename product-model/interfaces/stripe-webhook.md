---
{
  "type": "webhook",
  "actors": [
    "stripe"
  ],
  "entryPoints": [
    {
      "webhook": "/webhook/stripe/"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/urls.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/urls.py"
    }
  ]
}
---

# Stripe webhook

Payment, subscription-deletion and card-attachment events.
