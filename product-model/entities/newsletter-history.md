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

# Newsletter history

An independently identified Newsletter history. Actor-visible log/projections over retained accounting. Owner display requires current associations; administrative totals can include orphaned accounting.

## Information kept

- **Post association** — Nullable link from recipient accounting to the writing selected for dispatch.
- **Blog/subscriber association** — Nullable link to recipient enrollment and its currently associated Blog.
- **Current Post title** — Current title from linked writing, rather than a frozen copy of sent content.
- **Current Post link** — Current linked writing address, reflecting its current permalink and path.
- **Recorded date** — Maximum accounting time in the owner-visible writing group; an accounting time is recorded before SMTP.
- **Recipient count** — Count of records contributing to the currently linked owner-visible writing group.
- **Retained accounting count** — Administrative total of retained records, including accounting with removed associations.
