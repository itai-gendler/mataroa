---
{
  "type": "web",
  "actors": [
    "reader",
    "author",
    "administrator"
  ],
  "entryPoints": [
    {
      "web": "/"
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

# Web

Public writing, author workspace and custom moderation.
