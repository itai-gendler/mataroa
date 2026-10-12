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
      "text": "A Zola archive provides all owned Posts and its base configuration, without complete Pages/images.",
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

# Zola

## Trigger

Zola: Export blog.

## Outcome

A Zola archive provides all owned Posts and its base configuration, without complete Pages/images.
