---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author confirms permanent removal of their identity and owned writing.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::blog-settings"
        }
      },
      "capability": "delete-account"
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
        "web": {
          "place": "web::authenticated::blog-settings"
        }
      },
      "capability": "delete-account"
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
        "web": {
          "place": "web::authenticated::blog-settings"
        }
      },
      "actor": "author",
      "capability": "delete-account"
    },
    {
      "text": "After local deletion, the product redirects the participant to the public landing information.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "delete-account",
      "contexts": {
        "web": {
          "place": "web::authenticated::blog-settings"
        }
      }
    },
    {
      "text": "The caller requests shipped product information or a guide.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::public::about-mataroa"
        }
      },
      "capability": "read-about-mataroa"
    },
    {
      "text": "The requested fixed landing information or shipped guide is presented.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::public::about-mataroa"
        }
      },
      "actor": "author",
      "capability": "read-about-mataroa"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#UserDelete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#methodology"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#comparisons"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#guides_markdown"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#guides_images"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#guides_comments"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#guides_post_by_email"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/export.py"
    }
  ]
}
---

# Owner deleted

## Trigger

A locally Premium author confirms permanent deletion and the remote cancellation succeeds.

## Outcome

Remote cancellation succeeds, then the identity and owned writing/captures are deleted; subscriber associations become absent and the public landing redirect follows. The requested fixed landing information or shipped guide is presented.

## Edge cases

- A linked subscription’s Blog association becomes absent; notification accounting may retain nullable links, while external customers/cards are not universally deleted.
