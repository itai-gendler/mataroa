---
{
  "appliesTo": [
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

# Username accepts lowercase letters, digits and hyphens, at most 150 characters; only-hyphen and reserved names are refused, and username is unique

Username accepts lowercase letters, digits and hyphens, at most 150 characters; only-hyphen and reserved names are refused, and username is unique. Optional email is not unique.
