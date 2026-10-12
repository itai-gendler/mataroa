---
{
  "kind": "person",
  "acts": "external",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/urls.py"
    }
  ],
  "relations": [
    {
      "entity": "account",
      "verb": "has",
      "cardinality": "one-to-one"
    }
  ]
}
---

# Administrator

Custom moderation reports and approval operations.
