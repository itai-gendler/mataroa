---
{
  "kind": "validation",
  "routes": {
    "p-sign-up": "P SIGN UP"
  },
  "steps": [
    {
      "text": "The prospective author completes the onboarding continuation and supplies username, optional email and password.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-sign-up": {
          "place": "web::public::sign-up"
        }
      }
    },
    {
      "text": "Invalid fields, reserved or conflicting names are reported without a new identity.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p-sign-up": {
          "place": "web::public::sign-up"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#UserCreateStepOne"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#UserCreateStepTwo"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/forms.py#UserCreationForm"
    }
  ]
}
---

# Invalid fields or name

## Trigger

Invalid fields or name: Create account.

## Outcome

Invalid fields, reserved or conflicting names are reported without a new identity.
