---
{
  "entities": [
    {
      "entity": "image",
      "shows": [
        "Name",
        "Hosted content",
        "Extension",
        "Address",
        "Uploaded time"
      ],
      "collects": [
        "Name"
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

# Image

Selected hosted content, saved name, address, upload time and links to writing that references it; rename and deletion operate on this subject.
