---
{
  "kind": "primary",
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
      "text": "The two-stage onboarding creates the identity, logs in the new author and redirects to the dashboard.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "creates",
          "facts": [
            "Username",
            "Email",
            "Password credential",
            "API key",
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
        },
        {
          "entity": "blog",
          "effect": "creates",
          "facts": [
            "Title",
            "Byline",
            "Rendered byline",
            "Footer",
            "Rendered footer",
            "Canonical address",
            "Proper address",
            "Custom domain",
            "Retirement destination",
            "Theme preferences",
            "Alternative post path",
            "Comments enabled",
            "Newsletter enabled",
            "Mail export enabled",
            "Automatic backups enabled",
            "Export-stop link",
            "Webring name",
            "Webring information address",
            "Previous Webring address",
            "Next Webring address"
          ],
          "with": "account"
        }
      ],
      "contexts": {
        "p-sign-up": {
          "place": "web::public::sign-up"
        }
      },
      "actor": "author"
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

# Completed

## Trigger

Completed: Create account.

## Outcome

The two-stage onboarding creates the identity, logs in the new author and redirects to the dashboard.

## Edge cases

- Creation generates the unique API key, join time and export-stop key; the new identity is active, with Premium, grandfathering, approval and delisting false and no processor/customer/subscription or Monero association.
- The dependent Blog starts titled with the username; comments, mail exports, automatic backups, themes and alternative post path are off, newsletter is on, optional byline/domain/retirement/Webring data are absent and the default footer contains RSS/email/Mataroa links.
- A supplied safe local continuation can replace the default dashboard destination; used onboarding codes do not create another identity.
