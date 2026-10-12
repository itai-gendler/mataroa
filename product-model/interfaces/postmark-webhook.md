---
{
  "type": "webhook",
  "actors": [
    "postmark"
  ],
  "entryPoints": [
    {
      "webhook": "/webhook/postmark/"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/urls.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/urls.py"
    }
  ]
}
---

# Postmark webhook

Inbound email delivery with configured basic credentials.
