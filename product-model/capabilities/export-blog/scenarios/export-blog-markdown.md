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
      "text": "A ZIP provides all owned Posts and Pages as Markdown, including undated/future entries and no image binaries; undated export dates use creation dates.",
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
            "Created time"
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
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Markdown content"
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

# Markdown

## Trigger

Markdown: Export blog.

## Outcome

A ZIP provides all owned Posts and Pages as Markdown, including undated/future entries and no image binaries; undated export dates use creation dates.
