---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post-backup"
    },
    {
      "type": "entity",
      "id": "blog"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py"
    }
  ]
}
---

# Captures store cleaned text independently of a live Post, use Untitled for an empty title and keep the newest 250 by identity order

Captures store cleaned text independently of a live Post, use Untitled for an empty title and keep the newest 250 by identity order. Automatic browser capture is enabled by its preference and debounced at 2500 milliseconds; the endpoint has no preference eligibility check.
