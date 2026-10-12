---
{
  "entities": [
    {
      "entity": "post",
      "shows": [
        "Title",
        "Slug",
        "Markdown content",
        "Rendered content",
        "Canonical link",
        "Proper link",
        "Updated time",
        "Publication date",
        "Publication status"
      ],
      "collects": [
        "Title",
        "Slug",
        "Markdown content",
        "Publication date"
      ]
    },
    {
      "entity": "comment",
      "shows": [
        "Rendered content",
        "Name",
        "Created time",
        "Link",
        "Author marker",
        "Approval",
        "Email"
      ],
      "collects": [
        "Content",
        "Name",
        "Email"
      ]
    },
    {
      "entity": "post-views",
      "shows": [
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
    },
    {
      "entity": "post-backup",
      "shows": [
        "Title",
        "Content",
        "Saved time"
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

# Post

Selected writing with its rendered content and disclosed responses; owner editing and deletion are stages of this subject.
