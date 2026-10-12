---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author ends the current session.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::dashboard"
        }
      },
      "capability": "log-out"
    },
    {
      "text": "The session ends and the product redirects to its public landing information.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::authenticated::dashboard"
        }
      },
      "capability": "log-out"
    },
    {
      "text": "Ending the session redirects the participant to the public landing information.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "log-out",
      "contexts": {
        "web": {
          "place": "web::authenticated::dashboard"
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
      "target": "main/views/general.py#Logout"
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

# Default logout

## Trigger

Sign out and reach public product information.

## Outcome

The session ends and the product redirects to its public landing information. The requested fixed landing information or shipped guide is presented.
