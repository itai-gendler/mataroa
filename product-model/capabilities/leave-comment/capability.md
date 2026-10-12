---
{
  "availability": [
    {
      "place": "web::public"
    },
    {
      "place": "web::authenticated"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#CommentCreate"
    }
  ]
}
---

# Leave comment

The valid ordinary response is saved pending and an owner-review email is attempted before returning to the selected writing.
