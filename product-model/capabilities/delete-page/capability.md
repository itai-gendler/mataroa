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
      "target": "main/views/general.py#PageDelete"
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

# Delete page

The selected static writing is removed; web redirects to the remaining collection.
