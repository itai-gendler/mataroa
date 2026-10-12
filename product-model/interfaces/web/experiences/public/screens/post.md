---
{
  "entities": [
    {
      "entity": "post",
      "shows": [
        "Title",
        "Publication date",
        "Publication status",
        "Canonical link",
        "Proper link",
        "Rendered content",
        "Updated time"
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
        "Approval"
      ],
      "collects": [
        "Content",
        "Name",
        "Email"
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
