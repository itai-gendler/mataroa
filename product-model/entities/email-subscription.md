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

# Email subscription

An independently identified Email subscription. Blog association can become absent after Account deletion.

## Information kept

- **Blog association** — The selected Blog; becomes absent when its owning identity is removed.
- **Email** — Validated recipient address, unique within the selected Blog; enrollment does not verify address control.
- **Unsubscribe link** — Derived globally keyed removal address, generated at creation.
- **Active** — True at new enrollment or reactivation; false after address deactivation.

## States

### Active

Selected for recipient processing.

### Inactive

Retained without recipient selection.
