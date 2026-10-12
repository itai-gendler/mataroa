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
      "target": "main/views/api.py#APIKeyReset"
    }
  ],
  "domain": "api"
}
---

# Reset API key

A new random key replaces the current key and is revealed; the replaced bearer no longer resolves.
