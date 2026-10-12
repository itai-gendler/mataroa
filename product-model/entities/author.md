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
    },
    {
      "entity": "connected-application",
      "verb": "connects",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Author

Account creation and operation of owned writing.
