---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Username",
        "Email"
      ],
      "collects": [
        "Username",
        "Email"
      ]
    },
    {
      "entity": "blog",
      "shows": [
        "Title",
        "Byline",
        "Footer",
        "Custom domain",
        "Retirement destination",
        "Theme preferences",
        "Alternative post path",
        "Comments enabled",
        "Newsletter enabled",
        "Mail export enabled"
      ],
      "collects": [
        "Title",
        "Byline",
        "Footer",
        "Custom domain",
        "Retirement destination",
        "Theme preferences",
        "Alternative post path",
        "Comments enabled",
        "Newsletter enabled",
        "Mail export enabled"
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

# Blog settings

Profile identity and Blog preferences, including monthly export and newsletter switches; the retirement field is available only under its eligibility rule.
