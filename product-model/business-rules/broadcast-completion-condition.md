---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post"
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

# A real run records completion when no recipient exception was recorded, including an empty recipient list

A real run records completion when no recipient exception was recorded, including an empty recipient list. A recipient failure keeps completion absent. Edits, clearing a date and rescheduling do not reset completion.
