---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "send-post-notifications"
    },
    {
      "type": "entity",
      "id": "newsletter-history"
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

# Dispatch records pair accounting before SMTP

Dispatch records pair accounting before SMTP. Owner projections require current linked Post/subscriber associations and show current title/link, recipient count and maximum time. Removed associations alter the projection; administrative totals can count retained orphan accounting. Accounting does not prove delivery.
