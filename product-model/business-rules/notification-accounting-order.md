---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post"
    },
    {
      "type": "entity",
      "id": "email-subscription"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/management/commands/processnotifications.py"
    }
  ]
}
---

# Unique recipient/Post accounting is created before mail construction and SMTP; a retained pair suppresses a repeated attempt and send return counts are ignored

Unique recipient/Post accounting is created before mail construction and SMTP; a retained pair suppresses a repeated attempt and send return counts are ignored. Recipient exceptions normally delete a just-created record and notify administrators. If failure precedes current assignment, function-local record/created can still refer to a prior recipient.
