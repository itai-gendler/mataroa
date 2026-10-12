---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "image"
    },
    {
      "type": "entity",
      "id": "account"
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

# Allowed extensions are jpeg, jpg, png, svg, gif, webp, tiff, tif and bmp; jpg becomes the jpeg label without byte conversion

Allowed extensions are jpeg, jpg, png, svg, gif, webp, tiff, tif and bmp; jpg becomes the jpeg label without byte conversion. Individual size is at most 1,100,000 bytes and total owned bytes at most 1,000,000,000. Files persist sequentially; no enforced 1000-image count or byte-content verification is claimed.
