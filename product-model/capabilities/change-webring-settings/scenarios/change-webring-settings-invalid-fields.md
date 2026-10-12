---
{
  "kind": "validation",
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
      "text": "Invalid Webring fields leave the current settings unchanged.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "w-webring": {
          "place": "web::authenticated::webring"
        }
      }
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

# Invalid fields

## Trigger

Invalid fields: Change webring settings.

## Outcome

Invalid Webring fields leave the current settings unchanged.
