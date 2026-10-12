---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "connected-application"
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
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/mcp/server.py"
    }
  ]
}
---

# Fixed tools are open_posts, search_mentions, list_posts, get_post, create_draft, update_draft, publish_post, delete_post, list_pages, get_page, list_comments and get_comment

Fixed tools are open_posts, search_mentions, list_posts, get_post, create_draft, update_draft, publish_post, delete_post, list_pages, get_page, list_comments and get_comment. Every tool requires baseline read, and mutations require their additional scope. Owner binding ignores attempted override; arguments/pagination are strict, with lists bounded at 100 and mention search at 20. Delegated response output excludes commenter email. Native reader remains read-only and exposes public links only for Published writing.
