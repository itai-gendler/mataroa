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
      "target": "main/views/general.py#BlogImport"
    }
  ]
}
---

# Import posts

Each UTF-8 text file becomes an undated entry whose title comes from its filename; completion redirects to the Blog.
