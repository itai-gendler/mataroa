---
{
  "kind": "primary",
  "routes": {
    "p-post": "P POST",
    "w-post": "W POST"
  },
  "steps": [
    {
      "text": "The caller submits response text, optional identity fields and spam-control input.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-post": {
          "place": "web::public::post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        }
      }
    },
    {
      "text": "Honeypot or invalid/expired/too-fast signed timing acknowledges the submission without persistence.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p-post": {
          "place": "web::public::post"
        },
        "w-post": {
          "place": "web::authenticated::post"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#CommentCreate"
    }
  ]
}
---

# Spam shaped drop

## Trigger

Spam shaped drop: Leave comment.

## Outcome

Honeypot or invalid/expired/too-fast signed timing acknowledges the submission without persistence.
