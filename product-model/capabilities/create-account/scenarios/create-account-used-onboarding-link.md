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
      "text": "A used onboarding continuation redirects to the index without another creation.",
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

# Used onboarding link

## Trigger

Used onboarding link: Create account.

## Outcome

A used onboarding continuation redirects to the index without another creation.
