---
{
  "type": "messaging",
  "actors": [
    "author"
  ],
  "entryPoints": [
    {
      "messaging": "post@<username>.mataroa.blog"
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

# Post by email

Subject/text writing to the documented post or draft address, with a resulting link reply.
