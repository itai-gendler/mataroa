---
{
  "kind": "primary",
  "routes": {
    "w-import-posts": "W IMPORT POSTS"
  },
  "steps": [
    {
      "text": "The author submits UTF-8 text files.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-import-posts": {
          "place": "web::authenticated::import-posts"
        }
      }
    },
    {
      "text": "Each UTF-8 text file becomes an undated entry whose title comes from its filename; completion redirects to the Blog.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "creates",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Rendered content",
            "Canonical link",
            "Proper link",
            "Created time",
            "Updated time",
            "Publication date",
            "Publication status",
            "Discovery eligibility",
            "Revision fingerprint",
            "Broadcast completion",
            "Newsletter eligibility",
            "Excerpt"
          ]
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "w-import-posts": {
          "place": "web::authenticated::import-posts"
        }
      },
      "actor": "author"
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

# Files become drafts

## Trigger

Files become drafts: Import posts.

## Outcome

Each UTF-8 text file becomes an undated entry whose title comes from its filename; completion redirects to the Blog.
