---
{
  "kind": "primary",
  "routes": {
    "w-blog-settings": "W BLOG SETTINGS"
  },
  "steps": [
    {
      "text": "The author confirms permanent removal of their identity and owned writing.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-blog-settings": {
          "place": "web::authenticated::blog-settings"
        }
      }
    },
    {
      "text": "The current Premium subscription is canceled successfully before local identity removal.",
      "kind": "product",
      "actor": "author",
      "entities": [
        {
          "entity": "premium-subscription",
          "effect": "removes"
        }
      ],
      "contexts": {
        "w-blog-settings": {
          "place": "web::authenticated::blog-settings"
        }
      }
    },
    {
      "text": "Remote cancellation succeeds, then the identity and owned writing/captures are deleted; subscriber associations become absent and the public landing redirect follows.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "removes"
        },
        {
          "entity": "blog",
          "effect": "removes",
          "with": "account"
        },
        {
          "entity": "post",
          "effect": "removes",
          "with": "blog"
        },
        {
          "entity": "page",
          "effect": "removes",
          "with": "blog"
        },
        {
          "entity": "image",
          "effect": "removes",
          "with": "blog"
        },
        {
          "entity": "post-backup",
          "effect": "removes",
          "with": "account"
        },
        {
          "entity": "comment",
          "effect": "removes",
          "with": "post",
          "from": "Approved",
          "as": "approved-responses"
        },
        {
          "entity": "comment",
          "effect": "removes",
          "with": "post",
          "from": "Pending",
          "as": "pending-responses"
        },
        {
          "entity": "post-views",
          "effect": "removes",
          "with": "post"
        },
        {
          "entity": "page-views",
          "effect": "removes",
          "with": "blog"
        },
        {
          "entity": "email-subscription",
          "effect": "changes",
          "facts": [
            "Blog association"
          ]
        }
      ],
      "contexts": {
        "w-blog-settings": {
          "place": "web::authenticated::blog-settings"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#UserDelete"
    }
  ]
}
---

# Owner deleted

## Trigger

A locally Premium author confirms permanent deletion and the remote cancellation succeeds.

## Outcome

Remote cancellation succeeds, then the identity and owned writing/captures are deleted; subscriber associations become absent and the public landing redirect follows.

## Edge cases

- A linked subscription’s Blog association becomes absent; notification accounting may retain nullable links, while external customers/cards are not universally deleted.
