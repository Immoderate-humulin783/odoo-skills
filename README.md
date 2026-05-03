# Odoo Skills

Agent skills for practical Odoo addon work and OCA module migrations.

## Quick Start

Link the skills into your local Claude skills directory:

```bash
./scripts/link-skills.sh
```

If your Odoo source checkout is outside the project being edited, export its path so agents can inspect framework code when needed. You can also expose the local development command and tool README that describe how this machine runs Odoo:

```bash
export ODOO_SOURCE=/path/to/odoo
export ODOO_BASE_COMMAND="/path/to/odoo/odoo-bin -c /path/to/odoo.conf --addons-path=/path/to/addons"
export ODOO_TOOL_README=/path/to/local-development/README.md
```

Put those exports in your shell profile if you want them available in every agent session.

`ODOO_BASE_COMMAND` is the base command agents should inspect before proposing install/update/test commands. `ODOO_TOOL_README` points to local setup documentation agents should read before using project-specific tooling.

## Skills

- **[grill-me](./skills/grill-me/SKILL.md)** - Odoo-specific grilling session for stress-testing addon plans, security, data models, UI flows, OWL changes, migrations, and verification strategy.
- **[owl](./skills/owl/SKILL.md)** - OWL frontend engineering for Odoo and standalone Owl apps, including components, templates, reactivity, hooks, plugins, debugging, and migration.
- **[odoo](./skills/odoo/SKILL.md)** - Odoo addon development, codebase exploration, debugging, architecture review, and manifest/docs sync.
- **[odoo-guidelines](./skills/odoo-guidelines/SKILL.md)** - Official Odoo coding guideline review for module structure, XML, Python, translations, JavaScript, and SCSS.
- **[odoo-migration](./skills/odoo-migration/SKILL.md)** - End-to-end OCA module migration workflow for porting addons between Odoo major versions.

## Scope

These skills focus on Odoo addon engineering. The migration skill covers OCA module migration and `[MIG]` pull request preparation. OpenUpgrade workflows are intentionally out of scope.
