---
{
  "availability": [
    {
      "place": "web::public"
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

# Create account

The two-stage onboarding creates the identity, logs in the new author and redirects to the dashboard.
