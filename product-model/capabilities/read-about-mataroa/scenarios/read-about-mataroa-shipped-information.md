---
{
  "kind": "primary",
  "routes": {
    "p-about-mataroa": "P ABOUT MATAROA",
    "p-export-blog": "P EXPORT BLOG",
    "w-about-mataroa": "W ABOUT MATAROA",
    "w-export-blog": "W EXPORT BLOG"
  },
  "steps": [
    {
      "text": "The caller requests shipped product information or a guide.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-about-mataroa": {
          "place": "web::public::about-mataroa"
        },
        "p-export-blog": {
          "place": "web::public::export-blog"
        },
        "w-about-mataroa": {
          "place": "web::authenticated::about-mataroa"
        },
        "w-export-blog": {
          "place": "web::authenticated::export-blog"
        }
      }
    },
    {
      "text": "The requested fixed landing information or shipped guide is presented.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "p-about-mataroa": {
          "place": "web::public::about-mataroa"
        },
        "p-export-blog": {
          "place": "web::public::export-blog"
        },
        "w-about-mataroa": {
          "place": "web::authenticated::about-mataroa"
        },
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
      "target": "main/views/general.py#methodology"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#comparisons"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#guides_markdown"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#guides_images"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#guides_comments"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#guides_post_by_email"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/export.py"
    }
  ]
}
---

# Shipped information

## Trigger

Shipped information: Read about mataroa.

## Outcome

The requested fixed landing information or shipped guide is presented.
