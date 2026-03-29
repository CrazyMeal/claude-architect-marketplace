# Claude Architect Marketplace — Contributor Guide

This repository is a **Claude Code plugin marketplace** containing 5 architecture plugins. When contributing, you are editing plugin definitions — skills, commands, agents, and shared knowledge — not application code.

## Repository Structure

```
.claude-plugin/
  plugin.json          # Root marketplace manifest
  marketplace.json     # Catalog listing all plugins with their versions

plugins/
  architecture-design/     # System & component design (DDD, distributed systems)
  architecture-analysis/   # Codebase analysis, dependency analysis
  diagrams-as-code/        # C4 diagrams, PlantUML/Mermaid/D2 generation
  architecture-docs/       # ADRs (MADR), tech specs, RFCs
  architecture-review/     # ATAM-style reviews, risk assessment

shared/
  core-knowledge.md        # QA metrics, trade-off pairs, pattern catalog, DDD reference
  c4-templates.md          # PlantUML C4 syntax and templates
  output-conventions.md    # Mandatory artifact locations, naming, cross-reference rules
  implementation-guide.md  # How implementation agents discover the right doc file
```

Each plugin follows this structure:

```
plugins/<name>/
  .claude-plugin/plugin.json   # Plugin manifest (name, version, description)
  agents/<agent>.md            # Agent persona definition
  skills/<skill>/SKILL.md      # Skill definition with trigger description
  commands/<command>.md        # Slash command prompt
  references/                  # Reference docs loaded on demand (not all plugins)
  templates/                   # Templates loaded on demand (not all plugins)
```

## Versioning Convention

**Independent plugin versioning** — each plugin has its own version. When you change a plugin, bump only that plugin's version (semver minor for new features, patch for fixes).

After bumping a plugin version, always update **both**:
1. `plugins/<name>/.claude-plugin/plugin.json` — the source of truth
2. `.claude-plugin/marketplace.json` — the catalog entry for that plugin (must match)

Bump the **root marketplace version** (`.claude-plugin/plugin.json` + `.claude-plugin/marketplace.json` top-level) whenever any plugin changes, as it represents the overall release.

Current versions:
| Plugin | Version |
|--------|---------|
| architecture-design | 1.7.0 |
| architecture-docs | 1.7.0 |
| architecture-analysis | 1.6.0 |
| architecture-review | 1.6.0 |
| diagrams-as-code | 1.6.0 |
| Marketplace | 1.8.0 |

## Shared Knowledge

`shared/` files are loaded on-demand (referenced explicitly in skill/command prompts). They are **not** auto-injected. Reference them only when the content is needed. Do not modify shared files unless the change applies across all plugins.

`shared/output-conventions.md` is the **authoritative source** for where artifacts go (`docs/adr/`, `docs/diagrams/`, `docs/specs/`, `docs/rfcs/`, `docs/reviews/`). Commands must use these paths consistently.

## Adding or Modifying a Plugin

1. **New skill**: Add `skills/<skill-name>/SKILL.md` with a clear `description` trigger in the frontmatter. The description is how Claude decides when to activate the skill — make it specific.
2. **New command**: Add `commands/<command>.md`. Commands are slash-command prompts, not code.
3. **Bump versions**: plugin `plugin.json` → `marketplace.json` entry → root `marketplace.json` version → root `plugin.json` version.

## CI Validation

`.github/workflows/validate.yml` runs on every PR touching `plugins/` or `.claude-plugin/`. It checks:
- JSON validity of all plugin files
- Required `README.md` presence per plugin
- All `source` paths in `marketplace.json` resolve to real directories
- No hardcoded secrets, dangerous shell patterns, or non-HTTPS URLs

Run `jq . <file>` locally to validate JSON before committing.
