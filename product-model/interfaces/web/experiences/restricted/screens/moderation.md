---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Username",
        "Email",
        "Joined date",
        "Premium",
        "Grandfathered",
        "Approved",
        "Processor customer",
        "Post count",
        "Image count",
        "Storage used"
      ]
    },
    {
      "entity": "blog",
      "shows": [
        "Title",
        "Proper address",
        "Custom domain"
      ]
    },
    {
      "entity": "post",
      "shows": [
        "Title",
        "Publication date",
        "Proper link",
        "Created time"
      ]
    },
    {
      "entity": "page",
      "shows": [
        "Title",
        "Link",
        "Created time"
      ]
    },
    {
      "entity": "comment",
      "shows": [
        "Created time",
        "Approval"
      ]
    },
    {
      "entity": "image",
      "shows": [
        "Size"
      ]
    },
    {
      "entity": "email-subscription",
      "shows": [
        "Active",
        "Blog association"
      ]
    },
    {
      "entity": "post-backup",
      "shows": [
        "Saved time"
      ]
    },
    {
      "entity": "newsletter-history",
      "shows": [
        "Retained accounting count"
      ]
    },
    {
      "entity": "post-views",
      "shows": [
        "Daily counts",
        "Total views"
      ]
    },
    {
      "entity": "page-views",
      "shows": [
        "Daily counts",
        "Total views",
        "Path"
      ]
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

# Moderation

Custom moderation report with the traced aggregate, collection or date-specific projections.
