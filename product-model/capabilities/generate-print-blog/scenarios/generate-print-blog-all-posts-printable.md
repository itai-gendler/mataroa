---
{
  "kind": "primary",
  "routes": {
    "w-export-blog": "W EXPORT BLOG"
  },
  "steps": [
    {
      "text": "The author requests printable writing.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-export-blog": {
          "place": "web::authenticated::export-blog"
        }
      }
    },
    {
      "text": "All owned writing is rendered as printable HTML; the product does not generate a PDF file.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Publication date",
            "Created time",
            "Rendered content"
          ]
        }
      ],
      "contexts": {
        "w-export-blog": {
          "place": "web::authenticated::export-blog"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/export.py#export_print"
    }
  ]
}
---

# All posts printable

## Trigger

All posts printable: Generate print blog.

## Outcome

All owned writing is rendered as printable HTML; the product does not generate a PDF file.
