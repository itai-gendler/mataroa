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
        "Content",
        "Rendered content",
        "Name",
        "Created time",
        "Link",
        "Author marker",
        "Approval"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "reader",
        "author"
      ],
      "when": [
        {
          "state": "Approved"
        },
        {
          "entity": "blog",
          "fact": "Comments enabled",
          "is": true
        }
      ]
    },
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

# Comment disclosure is limited to a public participant for approved responses or its owner

Comment disclosure is limited to a public participant for approved responses or its owner.

Response presentation on the writing detail also requires the associated Blog’s comments switch. The dedicated pending-review surface does not use that switch.
