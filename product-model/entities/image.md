---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/models.py"
    }
  ]
}
---

# Image

An independently identified Image. Existing references are not rewritten on deletion.

## Information kept

- **Name** — Original filename or later owner-supplied name, independent of the hosted address.
- **Hosted content** — Saved uploaded bytes; extension checks do not verify the byte content.
- **Extension** — Allowed file label, normalizing jpg to jpeg without conversion or content verification.
- **Address** — Globally unique hosted address derived from the generated image identity and extension.
- **Size** — Stored byte length.
- **Uploaded time** — Upload time.
