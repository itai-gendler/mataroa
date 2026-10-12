---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account"
    },
    {
      "type": "entity",
      "id": "post"
    },
    {
      "type": "entity",
      "id": "page"
    },
    {
      "type": "entity",
      "id": "comment"
    },
    {
      "type": "entity",
      "id": "image"
    },
    {
      "type": "entity",
      "id": "post-views"
    },
    {
      "type": "entity",
      "id": "page-views"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/views/moderation.py"
    }
  ]
}
---

# Reports use implemented counts, activity/cohort groups and top request-count projections

Reports use implemented counts, activity/cohort groups and top request-count projections. Users list filters nonapproved/nonempty/Premium and paginates at 100. Approve/unapprove change only Approved. Public serving does not enforce approval; delisting warnings do not establish external search-engine removal. The shipped delete link goes to generic administration.
