---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/general.py"
    }
  ]
}
---

# Ordinary valid submission starts Pending and attempts owner mail containing review links; author-marked submission starts Approved with the caller username

Ordinary valid submission starts Pending and attempts owner mail containing review links; author-marked submission starts Approved with the caller username. Mail exceptions occur after save.
