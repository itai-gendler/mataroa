---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account"
    },
    {
      "type": "entity",
      "id": "premium-subscription"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py"
    }
  ]
}
---

# A prepared processor customer is kept and an existing subscription is reused

An absent customer can be created and saved before later failure. Existing initial subscription is reused except missing/canceled/incomplete-expired; active/trialing redirects rather than enabling locally. Missing invoice confirmation secret reports unavailable.
