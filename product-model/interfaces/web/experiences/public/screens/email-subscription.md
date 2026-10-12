---
{
  "entities": [
    {
      "entity": "blog",
      "shows": [
        "Title",
        "Proper address"
      ]
    },
    {
      "entity": "email-subscription",
      "shows": [
        "Email",
        "Active",
        "Unsubscribe link"
      ],
      "collects": [
        "Email"
      ]
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

# Email subscription

Enrollment, address deactivation and keyed removal for the selected Blog.
