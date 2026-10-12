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
      "id": "image"
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

# Markdown ZIP includes all Posts and Pages, without image bytes

Markdown ZIP includes all Posts and Pages, without image bytes. Hugo/Zola contain all Posts and base files, using fixed username.mataroa.blog addresses, without full Pages/images. EPUB includes all Posts and owned images but excludes Pages. Print is all-Post HTML. Draft export dates can use creation dates; import is not complete account restoration.
