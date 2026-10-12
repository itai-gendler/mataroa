---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::public::post"
        },
        {
          "place": "web::authenticated::post"
        }
      ],
      "facts": [
        "Email"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "contains",
          "entity": "post"
        },
        {
          "verb": "contains",
          "entity": "blog"
        },
        {
          "verb": "holds",
          "entity": "account"
        },
        {
          "verb": "has",
          "entity": "author"
        }
      ],
      "when": [
        {
          "entity": "blog",
          "fact": "Comments enabled",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/templates/main/post_detail.html"
    }
  ]
}
---

# Only the owner reads response email on enabled writing details

The selected writing’s response section is shown only while its Blog’s comments switch is on; supplied email is disclosed there only to the owner.
