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
      "target": "main/management/commands/processnotifications.py#Command.handle"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/management/commands/processnotifications.py#get_email"
    }
  ],
  "domain": "newsletter"
}
---

# Send post notifications

A real scheduled run selects yesterday’s eligible writing and current active recipients, records each new pair before SMTP, attempts multipart mail and records completion when no recipient exception was recorded.
