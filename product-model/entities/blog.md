---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/models.py"
    }
  ],
  "relations": [
    {
      "entity": "post",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "page",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "image",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "email-subscription",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "page-views",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "newsletter-history",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Blog

An independently identified Blog. Addresses/rendering are derived.

## Information kept

- **Title** — Public title; signup initializes it to the username.
- **Byline** — Optional Markdown byline, initially absent.
- **Rendered byline** — Markdown rendering of the saved byline.
- **Footer** — Markdown footer initially linking RSS, email enrollment and Mataroa.
- **Rendered footer** — Markdown rendering of the saved footer.
- **Canonical address** — Username host under the configured canonical host, using the configured protocol.
- **Proper address** — Configured custom-domain address when present, otherwise the username-host address.
- **Custom domain** — Optional configured host, initially absent; ordinary settings add no Premium gate.
- **Retirement destination** — Optional external retirement host, initially absent.
- **Theme preferences** — Shipped presentation preferences, initially disabled.
- **Alternative post path** — Whether the alternate post address is used, initially false.
- **Comments enabled** — Ordinary response enrollment setting, initially false.
- **Newsletter enabled** — Whether email enrollment and dispatch are enabled, initially true.
- **Mail export enabled** — Monthly export preference, initially false.
- **Automatic backups enabled** — Automatic browser capture preference, initially false; it is not exposed in ordinary Blog settings.
- **Export-stop link** — Derived keyed stop address; initial key is generated and rotates when used.
- **Webring name** — Optional Webring name, initially absent.
- **Webring information address** — Optional Webring information link, initially absent.
- **Previous Webring address** — Optional previous-site link, initially absent.
- **Next Webring address** — Optional next-site link, initially absent.
