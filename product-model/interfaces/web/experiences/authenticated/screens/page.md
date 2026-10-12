---
{
  "entities": [
    {
      "entity": "page",
      "shows": [
        "Title",
        "Slug",
        "Markdown content",
        "Rendered content",
        "Link",
        "Hidden"
      ],
      "collects": [
        "Title",
        "Slug",
        "Markdown content",
        "Hidden"
      ]
    },
    {
      "entity": "page-views",
      "shows": [
        "Path",
        "Daily counts",
        "Total views"
      ]
    },
    {
      "entity": "image",
      "shows": [
        "Name",
        "Address"
      ],
      "collects": [
        "Name",
        "Hosted content",
        "Extension"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py"
    }
  ]
}
---

# Page

Selected static writing; hiding it affects listing rather than direct access.
