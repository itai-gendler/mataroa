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
      "target": "main/management/commands/mailexports.py#Command.handle"
    }
  ]
}
---

# Mail blog export

On the first day, enabled identities receive a generated Markdown ZIP by email with a keyed stop link; an export receipt follows the send call.
