---
{
  "entities": [
    {
      "entity": "post",
      "shows": [
        "Title",
        "Markdown content",
        "Publication date"
      ],
      "collects": [
        "Title",
        "Markdown content",
        "Publication date"
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

# New post

New writing title, body and calendar date, with inline hosted-content attachment and optional automatic editor capture.
