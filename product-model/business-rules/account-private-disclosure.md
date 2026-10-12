---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::api"
        },
        {
          "place": "web::authenticated::dashboard"
        },
        {
          "place": "web::authenticated::billing"
        },
        {
          "place": "web::authenticated::subscribe-premium"
        },
        {
          "place": "web::authenticated::premium-subscription"
        },
        {
          "place": "web::authenticated::new-card"
        },
        {
          "place": "web::authenticated::images"
        },
        {
          "place": "web::authenticated::connect-application"
        }
      ],
      "facts": [
        "Username",
        "Email",
        "API key",
        "Premium",
        "Grandfathered",
        "Processor customer",
        "Current subscription",
        "Monero address",
        "Image count",
        "Storage used",
        "Storage remaining"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has",
          "entity": "author"
        }
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

# Account disclosure is limited to its owner

Account disclosure is limited to its owner. The password credential is collected and changed without disclosure.
