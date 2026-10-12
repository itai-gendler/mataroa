---
{
  "entities": [
    {
      "entity": "comment",
      "shows": [
        "Rendered content",
        "Name",
        "Email",
        "Created time",
        "Link",
        "Author marker",
        "Approval"
      ],
      "collects": [
        "Approval"
      ]
    },
    {
      "entity": "post",
      "shows": [
        "Title",
        "Proper link"
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

# Comment

Selected owned response with rendered text, supplied identity and review or deletion confirmation.
