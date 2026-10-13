---
{
  "kind": "configuration",
  "of": "capability-scenario",
  "settings": [
    {
      "entity": "account",
      "fact": "Grandfathered"
    },
    {
      "entity": "account",
      "fact": "Monero address"
    }
  ],
  "takesEffect": "Each time the author opens Billing. Staff set the Grandfathered flag and the Monero address in administration.",
  "stability": "Nothing is captured. A change applies the next time Billing is opened; an existing processor customer, subscription and cards stay as they are.",
  "alternatives": [
    {
      "id": "read-billing-grandfathered",
      "selectedWhen": "Grandfathered is true. It takes precedence over a Monero address."
    },
    {
      "id": "read-billing-monero",
      "selectedWhen": "Grandfathered is false and a Monero address is present."
    },
    {
      "id": "read-billing-stripe-overview",
      "selectedWhen": "Grandfathered is false and no Monero address is present. This is the default."
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/billing.py#billing_overview"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/templates/main/billing_overview.html"
    }
  ]
}
---

# Billing arrangement

Staff place each account on the Grandfather Plan, on Monero payment, or leave it on the processor subscription; all three are supported, and Billing shows a different form for each.
