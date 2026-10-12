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

# Comment

An independently identified Comment. Email is optional.

## Information kept

- **Content** — Saved response text.
- **Rendered content** — Allowlisted Markdown HTML derived from the saved response.
- **Name** — Optional supplied display name, with Anonymous fallback; author-marked submissions use the caller username.
- **Email** — Optional supplied address, withheld from public and delegated disclosure.
- **Created time** — Time the response was first saved.
- **Link** — Canonical parent-writing address with the response anchor.
- **Author marker** — False for ordinary creation and true for author-route creation.
- **Approval** — False for ordinary creation and true for author-marked creation.

## States

### Pending

Awaiting public approval.

### Approved

Included in public disclosure.
