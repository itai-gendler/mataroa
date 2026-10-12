---
{
  "kind": "primary",
  "routes": {
    "p-transparency": "P TRANSPARENCY",
    "w-transparency": "W TRANSPARENCY"
  },
  "steps": [
    {
      "text": "The caller requests the aggregate transparency projections.",
      "kind": "actor",
      "entities": [],
      "actor": "author",
      "contexts": {
        "p-transparency": {
          "place": "web::public::transparency"
        },
        "w-transparency": {
          "place": "web::authenticated::transparency"
        }
      }
    },
    {
      "text": "Cached aggregate counts, writing/activity distributions and revenue/climate estimates are presented; non-null dated counts include future dates.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p-transparency": {
          "place": "web::public::transparency"
        },
        "w-transparency": {
          "place": "web::authenticated::transparency"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py#_calculate_transparency_stats"
    }
  ]
}
---

# Aggregate estimates

## Trigger

Aggregate estimates: Read business transparency.

## Outcome

Cached aggregate counts, writing/activity distributions and revenue/climate estimates are presented; non-null dated counts include future dates.
