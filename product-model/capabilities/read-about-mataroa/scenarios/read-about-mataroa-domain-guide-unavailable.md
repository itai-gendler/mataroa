---
{
  "kind": "edge",
  "routes": {
    "p-about-mataroa": "P ABOUT MATAROA",
    "w-about-mataroa": "W ABOUT MATAROA"
  },
  "steps": [
    {
      "text": "The caller requests shipped product information or a guide.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-about-mataroa": {
          "place": "web::public::about-mataroa"
        },
        "w-about-mataroa": {
          "place": "web::authenticated::about-mataroa"
        }
      }
    },
    {
      "text": "Without custom-domain setup configuration the domain guide is unavailable.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p-about-mataroa": {
          "place": "web::public::about-mataroa"
        },
        "w-about-mataroa": {
          "place": "web::authenticated::about-mataroa"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#guides_customdomain"
    }
  ]
}
---

# Domain guide unavailable

## Trigger

Domain guide unavailable: Read about mataroa.

## Outcome

Without custom-domain setup configuration the domain guide is unavailable.
