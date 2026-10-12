---
{
  "scope": "Broad initial mapping of product-facing code at a035ac08b859d83575352f5bc3d27745065f4104.",
  "method": "Read-only tracked-file inventory and static tracing of entry points, checks, persistence and observable outcomes.",
  "covered": [
    {
      "description": "Product-facing handlers, local forms and business persistence; moderation deletion and inherited framework behavior remain gaps.",
      "paths": [
        "main/views/",
        "main/models.py",
        "main/forms.py",
        "main/validators.py",
        "main/text_processing.py"
      ]
    },
    {
      "description": "Hosting, public discovery, route bindings and configured product gates.",
      "paths": [
        "main/middleware.py",
        "main/feeds.py",
        "main/sitemaps.py",
        "main/urls.py",
        "mataroa/urls.py",
        "mataroa/settings.py"
      ]
    },
    {
      "description": "Functional template disclosure, editor capture/upload and processor-confirmation behavior.",
      "paths": [
        "main/templates/"
      ]
    },
    {
      "description": "Customer-observed subscriber dispatch and monthly export effects, excluding operator interaction contracts.",
      "paths": [
        "main/management/commands/processnotifications.py",
        "main/management/commands/mailexports.py",
        "deploy/templates/mataroa-notifications.timer",
        "deploy/templates/mataroa-notifications.service",
        "deploy/templates/mataroa-exports.timer"
      ]
    },
    {
      "description": "Export representation helpers and shipped base content.",
      "paths": [
        "export_base_hugo/",
        "export_base_zola/",
        "export_base_epub/"
      ]
    },
    {
      "description": "Optional consent/token lifecycle, owner-bound tool behavior and native reader, excluding detailed wire versions and external-host protocol.",
      "paths": [
        "mataroa/oauth.py",
        "main/mcp/",
        "main/views/mcp.py",
        "main/static/mcp/"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "Generic administration CRUD and inherited staff/model permissions, OAuth-client administration and admin grant revocation.",
      "paths": [
        "main/admin.py"
      ]
    },
    {
      "description": "Unlinked custom moderation user_delete supported-contract meaning; shipped link instead enters generic administration.",
      "paths": [
        "main/views/moderation.py"
      ]
    },
    {
      "description": "Operator preview/dry-run, reconciliation, renewal, administrative summary and OAuth cleanup contracts.",
      "paths": [
        "main/management/commands/"
      ]
    },
    {
      "description": "Exact inherited authentication and reset algorithms beyond local configuration, bindings, forms and destinations.",
      "paths": [
        "main/urls.py",
        "mataroa/settings.py"
      ]
    },
    {
      "description": "Detailed MCP wire-version and external host-protocol behavior.",
      "paths": [
        "main/views/mcp.py",
        "main/static/mcp/bridge.js"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Test fixtures and development/preview harness code.",
      "paths": [
        "main/tests/",
        "chatgpt/web/",
        "main/management/commands/devdata.py"
      ]
    },
    {
      "description": "Historical migration machinery.",
      "paths": [
        "main/migrations/"
      ]
    },
    {
      "description": "Provisioning, database backup and deployment mechanics apart from product-affecting timers/settings.",
      "paths": [
        "deploy/",
        "postgresql/",
        "docker-compose.yml"
      ]
    },
    {
      "description": "Build/package/CI machinery, framework bootstrapping and visual styling.",
      "paths": [
        ".github/",
        "pyproject.toml",
        "uv.lock",
        "manage.py",
        "mataroa/asgi.py",
        "mataroa/wsgi.py",
        "static/"
      ]
    }
  ],
  "limitations": [
    {
      "description": "Monero presentation is established here, but its activation/verification implementation is not established.",
      "paths": [
        "main/views/billing.py"
      ]
    },
    {
      "description": "SMTP send calls do not establish external delivery, and timer source does not establish deployment timezone/configuration.",
      "paths": [
        "main/management/commands/processnotifications.py",
        "main/management/commands/mailexports.py",
        "deploy/templates/mataroa-notifications.timer"
      ]
    },
    {
      "description": "Native bridge source does not establish external ChatGPT host identity or continuation.",
      "paths": [
        "main/static/mcp/bridge.js",
        "main/views/mcp.py"
      ]
    }
  ]
}
---

# Coverage
