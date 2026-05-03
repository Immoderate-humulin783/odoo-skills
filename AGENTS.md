# Odoo Agent Setup

Use these skills when working on Odoo addons, OCA repositories, or module migrations.

## Environment

If the Odoo framework source or local development setup is not discoverable inside the workspace, ask the user to configure:

```bash
export ODOO_SOURCE=/path/to/odoo
export ODOO_BASE_COMMAND="/path/to/odoo/odoo-bin -c /path/to/odoo.conf --addons-path=/path/to/addons"
export ODOO_TOOL_README=/path/to/local-development/README.md
```

When `$ODOO_SOURCE` is set, inspect it for framework APIs, migration helpers, XML syntax, assets, tests, and version-specific behavior before guessing.

When `$ODOO_BASE_COMMAND` is set, treat it as the local starting point for Odoo commands. Inspect it before proposing install/update/test commands, but still ask the user to confirm before running anything that touches a database or local service.

When `$ODOO_TOOL_README` is set, read it before using local development tools, wrappers, docker compose files, invoke tasks, make targets, or repo-specific Odoo commands.

## Repo Detection

Treat a repo as Odoo-related when it contains signals such as:

- `__manifest__.py`
- `odoo-bin`
- `addons/`
- `models/`
- `views/`
- `security/ir.model.access.csv`
- `controllers/`
- `static/src/`
- Odoo branch names like `16.0`, `17.0`, `18.0`, or `19.0`

## Skill Routing

- Use `grill-me` when the user wants to stress-test an Odoo plan/design, get grilled on addon architecture, clarify model/security/view choices before implementation, or says "grill me" in an Odoo context.
- Use `owl` for OWL/frontend component work, Odoo web client components, `@odoo/owl`, templates, hooks, reactivity, props, registries, plugins, assets, frontend debugging, and OWL migrations.
- Use `odoo` for addon development, exploration, debugging, architecture, manifests, docs, security, views, models, controllers, assets, reports, and tests.
- Use `odoo-guidelines` for official Odoo coding guideline checks, style reviews, module structure audits, XML/Python naming reviews, translation checks, JavaScript organization, and SCSS guideline checks.
- Use `odoo-migration` for OCA module migration, Odoo major-version ports, `[MIG]` PRs, and version checklist work.
- Do not use OpenUpgrade workflows for `odoo-migration`; that skill is scoped to normal OCA module migration.

## Command Safety

Before running Odoo install/update/test commands, inspect repo docs/config, `$ODOO_TOOL_README`, and `$ODOO_BASE_COMMAND` for the intended command, then ask the user to confirm. Odoo commands often need a database, addons path, config file, and local service assumptions.
