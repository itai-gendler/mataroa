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
      "entity": "blog",
      "verb": "holds",
      "cardinality": "one-to-one"
    },
    {
      "entity": "post-backup",
      "verb": "holds",
      "cardinality": "one-to-many"
    },
    {
      "entity": "premium-subscription",
      "verb": "has current",
      "cardinality": "one-to-one"
    },
    {
      "entity": "card",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "invoice",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Account

An independently identified Account. Counts/storage are derived. Email is optional and not unique. Password is collected/changed, not disclosed.

## Information kept

- **Username** — Unique lowercase letters, digits and hyphens, at most 150 characters; not solely hyphens and not reserved.
- **Email** — Optional contact/recovery address; not unique.
- **Password credential** — Collected or changed without disclosing the stored credential.
- **API key** — Unique random 32-character bearer secret; reset replaces it.
- **Joined date** — Time the identity was created.
- **Active** — Whether the identity remains active; new normal signup is active.
- **Premium** — Local Premium flag, initially false.
- **Grandfathered** — Existing grandfathered entitlement flag, initially false.
- **Redirect grandfathered** — Existing retirement-redirect entitlement flag, initially false.
- **Approved** — Custom moderation approval flag, initially false.
- **Delisted** — Warning flag for claimed search-engine delisting, initially false; it is not proof of external delisting.
- **Processor customer** — Associated external customer, initially absent.
- **Current subscription** — Associated external current subscription, initially absent.
- **Monero address** — External payment address, initially absent.
- **Post count** — Derived owned writing count.
- **Image count** — Derived owned hosted-image count.
- **Storage used** — Derived sum of owned hosted-byte sizes.
- **Storage remaining** — Derived remainder of the 1,000,000,000-byte allowance.
