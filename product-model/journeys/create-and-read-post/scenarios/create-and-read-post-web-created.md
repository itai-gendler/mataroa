---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Established continuation"
  },
  "steps": [
    {
      "text": "The author submits a title, body and current, future or blank calendar date in the editor.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::new-post"
        }
      },
      "capability": "create-post"
    },
    {
      "text": "Web creation saves title and cleaned body with the supplied or default current date and redirects to its HTML.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "creates",
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
            "Newsletter eligibility",
            "Excerpt"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::new-post"
        }
      },
      "actor": "author",
      "capability": "create-post"
    },
    {
      "text": "Saving new writing redirects the author to its HTML detail.",
      "kind": "product",
      "actor": "author",
      "entities": [],
      "capability": "create-post",
      "contexts": {
        "web": {
          "place": "web::authenticated::new-post"
        }
      }
    },
    {
      "text": "The caller requests the selected writing detail.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "web": {
          "place": "web::authenticated::post"
        }
      },
      "capability": "read-post"
    },
    {
      "text": "The selected HTML renders title, date and writing with its status and comments disclosure.",
      "kind": "product",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Title",
            "Rendered content",
            "Publication date",
            "Publication status",
            "Proper link"
          ]
        },
        {
          "entity": "comment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::authenticated::post"
        }
      },
      "actor": "author",
      "capability": "read-post"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PostCreate"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_posts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#postmark_webhook"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/backend.py#DjangoBlogBackend"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#PostDetail"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/api.py#api_post"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/static/mcp/posts.js"
    }
  ]
}
---

# Web created

## Trigger

Save new writing and follow the product’s redirect or own email reply to read it.

## Outcome

Web creation saves title and cleaned body with the supplied or default current date and redirects to its HTML. The selected HTML renders title, date and writing with its status and comments disclosure.
