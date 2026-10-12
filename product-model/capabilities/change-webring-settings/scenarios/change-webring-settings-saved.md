---
{
  "kind": "primary",
  "routes": {
    "w-webring": "W WEBRING"
  },
  "steps": [
    {
      "text": "The author supplies the Webring name and information, previous and next addresses.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "w-webring": {
          "place": "web::authenticated::webring"
        }
      }
    },
    {
      "text": "The four Webring fields are saved and the dashboard is reached.",
      "kind": "product",
      "entities": [
        {
          "entity": "blog",
          "effect": "changes",
          "facts": [
            "Webring name",
            "Webring information address",
            "Previous Webring address",
            "Next Webring address"
          ]
        }
      ],
      "contexts": {
        "w-webring": {
          "place": "web::authenticated::webring"
        }
      },
      "actor": "author"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#WebringUpdate"
    }
  ]
}
---

# Saved

## Trigger

Saved: Change webring settings.

## Outcome

The four Webring fields are saved and the dashboard is reached.

## Edge cases

- The local view does not add the ordinary login mixin; successful author use resolves the current identity, while uniform signed-out handling is not established.
