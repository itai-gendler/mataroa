---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "image",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::images"
        },
        {
          "place": "web::authenticated::new-post"
        },
        {
          "place": "web::authenticated::post"
        },
        {
          "place": "web::authenticated::new-page"
        },
        {
          "place": "web::authenticated::page"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
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

# Image creation is limited to its owner

Image creation is limited to its owner. Extension and byte-size validation remain input constraints, rather than additional plan privileges.
