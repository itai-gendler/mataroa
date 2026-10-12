---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::restricted"
        }
      ],
      "facts": [
        "Username",
        "Email",
        "Joined date",
        "Active",
        "Premium",
        "Grandfathered",
        "Redirect grandfathered",
        "Approved",
        "Delisted",
        "Processor customer",
        "Current subscription",
        "Monero address",
        "Post count",
        "Image count",
        "Storage used",
        "Storage remaining"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "administrator"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/moderation.py"
    }
  ]
}
---

# Account disclosure is limited to Administrator

Account disclosure is limited to Administrator.
