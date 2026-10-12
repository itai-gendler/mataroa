---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post"
    },
    {
      "type": "entity",
      "id": "blog"
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

# Selection uses precisely yesterday, absent completion and enabled newsletter; recipients are active at processing time

Selection uses precisely yesterday, absent completion and enabled newsletter; recipients are active at processing time. Publication itself does not invoke subscriber SMTP. No general overdue catch-up is implemented.
