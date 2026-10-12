---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The prospective author completes the onboarding continuation and supplies username, optional email and password.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::public::sign-up"
        }
      },
      "capability": "create-account"
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
        "web": {
          "place": "web::public::sign-up"
        }
      },
      "actor": "author",
      "capability": "create-account"
    },
    {
      "text": "Successful onboarding establishes the session and redirects the new author to the dashboard.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "create-account",
      "contexts": {
        "web": {
          "place": "web::public::sign-up"
        }
      }
    },
    {
      "text": "The author opens the dashboard overview.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::dashboard"
        }
      },
      "capability": "read-dashboard"
    },
    {
      "text": "The dashboard presents the current username, Blog identity, pending-response count and feature flags.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Premium",
            "Grandfathered"
          ]
        },
        {
          "entity": "blog",
          "effect": "reads",
          "facts": [
            "Title",
            "Comments enabled",
            "Newsletter enabled",
            "Automatic backups enabled"
          ]
        },
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Approval"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::dashboard"
        }
      },
      "actor": "author",
      "capability": "read-dashboard"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#dashboard"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/templates/main/dashboard.html"
    }
  ]
}
---

# Default signup

## Trigger

Start a Blog and reach its dashboard.

## Outcome

The two-stage onboarding creates the identity, logs in the new author and redirects to the dashboard. The dashboard presents the current username, Blog identity, pending-response count, feature flags.
