---
name: odoo-guidelines
description: Check Odoo code against the official Odoo coding guidelines, with practical review checklists for module structure, XML, Python, Odoo ORM patterns, translations, JavaScript, and SCSS. Use when the user asks to check Odoo guidelines, review coding style, validate module structure/naming, or audit an addon against official Odoo development conventions.
---

# Odoo Guidelines

Use this skill to review Odoo code against the official Odoo coding guidelines. It is a review/check skill, not a formatter.

## First Move

Identify:

- target Odoo version
- whether the code is on a stable branch or development branch
- addon/module scope
- changed files or review target
- repo-specific conventions and pre-commit tooling

If the Odoo source checkout is needed and not inside the workspace, inspect `$ODOO_SOURCE` when set. If local command/tooling context is needed, inspect `$ODOO_TOOL_README` and `$ODOO_BASE_COMMAND` before proposing checks.

## Stable Branch Rule

When modifying existing files in a stable version, existing file style supersedes generic guidelines. Do not recommend noisy restyling just to satisfy guidelines. Keep diffs minimal and focus on changed code, correctness, maintainability, and obvious guideline violations.

In development branches, apply the guidelines to modified code. Restructure an existing file only when most of the file is already under revision or the user explicitly asks for a broader cleanup.

## Review Workflow

1. Read [ODOO-CODING-GUIDELINES.md](ODOO-CODING-GUIDELINES.md).
2. Inspect changed files first unless the user asks for a full-addon audit.
3. Check module structure, file naming, XML, Python/Odoo patterns, translations, JS, and SCSS only where relevant.
4. Return findings first, ordered by severity, with file/line references.
5. Distinguish must-fix issues from low-value style cleanup.
6. State tests or checks run, and mention residual gaps.

## Output Format

Use code-review style output:

- Findings: severity, file/line, issue, why it matters, suggested fix.
- Open questions: only if needed.
- Checks run: commands or manual-only review.
- Summary: brief, after findings.

If there are no findings, say so explicitly and mention any guideline areas not checked.
