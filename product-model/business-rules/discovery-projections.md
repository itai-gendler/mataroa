---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post"
    },
    {
      "type": "entity",
      "id": "page"
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

# Visitor index and RSS select dates at most today

Visitor index and RSS select dates at most today. RSS takes the newest 100. Owner index also exposes undated/future writing. Sitemap includes index, due writing and non-hidden Pages.
