---
{
  "availability": [
    {
      "place": "web::authenticated"
    },
    {
      "place": "blog-api"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PageUpdate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_page"
    }
  ],
  "domain": "pages"
}
---

# Edit page

Validated static-writing fields and hidden choice persist; web retains the selected subject.
