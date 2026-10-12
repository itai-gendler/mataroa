---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account"
    },
    {
      "type": "entity",
      "id": "blog"
    },
    {
      "type": "entity",
      "id": "post"
    },
    {
      "type": "entity",
      "id": "page"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/management/commands/mailexports.py"
    }
  ]
}
---

# Only the first day processes enabled preferences, including identities with absent email

Only the first day processes enabled preferences, including identities with absent email. Each generated Markdown ZIP carries a stop link. A receipt follows SMTP; uncaught failures abort the run and no per-month deduplication is provided.
