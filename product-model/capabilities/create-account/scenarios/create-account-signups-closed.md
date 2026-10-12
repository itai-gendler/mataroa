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
      "text": "Both signup stages refuse new creation when deployment closes signups.",
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

# Signups closed

## Trigger

Signups closed: Create account.

## Outcome

Both signup stages refuse new creation when deployment closes signups.
