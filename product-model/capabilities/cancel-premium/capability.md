---
{
  "availability": [
    {
      "place": "web::authenticated"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#BillingCancel"
    }
  ],
  "domain": "billing"
}
---

# Cancel premium

Remote cancellation is scheduled at period end, administrative mail is attempted and local Premium remains until a deletion event.
