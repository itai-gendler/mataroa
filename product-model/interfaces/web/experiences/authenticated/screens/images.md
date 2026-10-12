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
        "Size",
        "Uploaded time"
      ],
      "collects": [
        "Name",
        "Hosted content",
        "Extension"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Image count",
        "Storage used",
        "Storage remaining"
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

# Images

Owned hosted-content library with count/storage amounts and sequential upload results.
