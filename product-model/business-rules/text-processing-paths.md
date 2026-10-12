---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post"
    },
    {
      "type": "entity",
      "id": "page"
    },
    {
      "type": "entity",
      "id": "comment"
    },
    {
      "type": "entity",
      "id": "blog"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/text_processing.py"
    }
  ]
}
---

# Writing cleanup removes selected control/surrogate characters and whitespace where invoked

Writing cleanup removes selected control/surrogate characters and whitespace where invoked. Import stores raw decoded text; web Page storage and API cleanup differ. Markdown HTML passes an allowlist, while delegated reader normalization further strips images/embeds/styles/identifiers.
