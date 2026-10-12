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
      "target": "main/text_processing.py"
    }
  ]
}
---

# Web/API normalize generated slugs and resolve collisions within the owner; manually chosen duplicates are refused

Web/API normalize generated slugs and resolve collisions within the owner; manually chosen duplicates are refused. Delegated creation also truncates to the 300-character bound and handles integrity conflicts.
