---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "read-post",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    },
    {
      "type": "entity",
      "id": "post-views"
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

# HTML detail records non-owner requests; source and hosted-byte reads do not create visits

HTML detail records non-owner requests; source and hosted-byte reads do not create visits. Recording is automatic and not a separate Scenario-created log entry.
