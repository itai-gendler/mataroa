---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-blog"
    },
    {
      "type": "capability",
      "id": "read-page"
    },
    {
      "type": "entity",
      "id": "page-views"
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

# Index and Page HTML record actual non-owner path visits

Index and Page HTML record actual non-owner path visits. RSS records all requests, including owner requests. Paths can identify index/RSS without a Page instance.
