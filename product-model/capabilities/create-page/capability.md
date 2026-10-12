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
      "target": "main/views/general.py#PageCreate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_pages"
    }
  ],
  "domain": "pages"
}
---

# Create page

Validated static writing is saved with a unique nonreserved permalink and hidden choice; web redirects to its HTML.
