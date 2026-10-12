---
{
  "kind": "primary",
  "routes": {
    "r-moderation": "R MODERATION",
    "r-posts": "R POSTS",
    "r-pages": "R PAGES"
  },
  "steps": [
    {
      "text": "The administrator selects the report, filter or reporting date.",
      "kind": "actor",
      "entities": [],
      "actor": "administrator",
      "contexts": {
        "r-moderation": {
          "place": "web::restricted::moderation"
        },
        "r-posts": {
          "place": "web::restricted::posts"
        },
        "r-pages": {
          "place": "web::restricted::pages"
        }
      }
    },
    {
      "text": "Aggregate, activity/cohort and top writing/path reports present their implemented input counts and rankings.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Joined date",
            "Post count",
            "Image count"
          ]
        },
        {
          "entity": "blog",
          "effect": "reads",
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
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Rendered content",
            "Canonical link",
            "Proper link",
            "Created time",
            "Updated time",
            "Publication date",
            "Publication status",
            "Discovery eligibility",
            "Revision fingerprint",
            "Broadcast completion",
            "Newsletter eligibility"
          ]
        },
        {
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Title",
            "Slug",
            "Markdown content",
            "Rendered content",
            "Link",
            "Hidden",
            "Created time",
            "Updated time"
          ]
        },
        {
          "entity": "image",
          "effect": "reads",
          "facts": [
            "Name",
            "Hosted content",
            "Extension",
            "Address",
            "Size",
            "Uploaded time"
          ]
        },
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Created time",
            "Approval"
          ]
        },
        {
          "entity": "email-subscription",
          "effect": "reads",
          "facts": [
            "Active",
            "Blog association"
          ]
        },
        {
          "entity": "post-backup",
          "effect": "reads",
          "facts": [
            "Title",
            "Content",
            "Saved time"
          ]
        },
        {
          "entity": "newsletter-history",
          "effect": "reads",
          "facts": [
            "Post association",
            "Blog/subscriber association",
            "Current Post title",
            "Current Post link",
            "Recorded date",
            "Recipient count",
            "Retained accounting count"
          ]
        },
        {
          "entity": "post-views",
          "effect": "reads",
          "facts": [
            "Visit times",
            "Daily counts",
            "Total views"
          ]
        },
        {
          "entity": "page-views",
          "effect": "reads",
          "facts": [
            "Path",
            "Visit times",
            "Daily counts",
            "Total views"
          ]
        }
      ],
      "contexts": {
        "r-moderation": {
          "place": "web::restricted::moderation"
        },
        "r-posts": {
          "place": "web::restricted::posts"
        },
        "r-pages": {
          "place": "web::restricted::pages"
        }
      },
      "actor": "administrator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/moderation.py"
    }
  ]
}
---

# Aggregate and top content reports

## Trigger

Aggregate and top content reports: Read moderation.

## Outcome

Aggregate, activity/cohort and top writing/path reports present their implemented input counts and rankings.
