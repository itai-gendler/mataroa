---
{
  "kind": "primary",
  "routes": {
    "w-export-blog": "W EXPORT BLOG"
  },
  "steps": [
    {
      "text": "The author requests the selected archive format.",
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
      "text": "An EPUB provides all owned Posts and owned images with canonical-image rewrites, without Pages.",
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
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": [
            "Title",
            "Canonical address",
            "Proper address"
          ]
        },
        {
          "entity": "image",
          "effect": "reads",
          "facts": [
            "Name",
            "Hosted content",
            "Extension",
            "Address"
          ]
        },
        {
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Markdown content"
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
      "target": "main/views/export.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/text_processing.py"
    }
  ]
}
---

# Epub

## Trigger

Epub: Export blog.

## Outcome

An EPUB provides all owned Posts and owned images with canonical-image rewrites, without Pages.
