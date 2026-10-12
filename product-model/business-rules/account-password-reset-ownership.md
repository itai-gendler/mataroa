---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::public::password-reset"
        }
      ],
      "facts": [
        "Password credential"
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

# Account modification is limited to its owner

Account modification is limited to its owner. The own continuation binds the identity before changing the credential.
