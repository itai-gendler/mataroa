---
{
  "id": "mataroa",
  "summary": "Minimal blogging with calendar publication, comments, subscriber email, portability and optional delegated writing.",
  "category": "blogging",
  "authors": [
    {
      "name": "Mataroa Contributors"
    }
  ],
  "license": "AGPL-3.0-only",
  "languages": [
    "en-US"
  ],
  "limitations": [
    "Draft and scheduled Post HTML remains accessible to anyone with its link.",
    "Subscriber mail processing selects yesterday’s dated writing rather than catching up every missed publication.",
    "Exports preserve different subsets of writing and hosted images.",
    "Comments cannot be edited through the supported contracts."
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "README.md"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "main/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "mataroa/settings.py"
    }
  ]
}
---

# Mataroa

Authors operate a minimal Blog with Posts and Pages, calendar publication dates, hosted images, comments, subscriber email, visit counts and portable writing. Billing offers Premium subscriptions and cards. Custom moderation presents reports and approval flags. The optional ChatGPT connection provides owner-bound draft writing, explicit publication, deletion and a native read-only Posts reader.

Discovery and direct HTML access differ: dates control listing and feeds, while unpublished HTML remains readable by link. Subscriber email is processed separately from publication. The ordinary bearer-key API and the delegated agent have independently established contracts.

## Intent

Give people who care about text a minimal place to just write and publish a Blog, with no ads, no tracking and no design options to manage, while their writing stays portable through exports and redirects to a new domain.
