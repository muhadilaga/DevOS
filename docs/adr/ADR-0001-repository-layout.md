# ADR-0001: Repository Layout

## Status

Accepted

## Context

DevOS needs a repository layout that separates policy, architecture, profiles, prompts, templates, scripts, tests, examples, assets, and documentation. The layout must support safe evolution and keep framework concerns distinct from project work.

## Decision

Use a layered repository structure with `core/` for rules, `profiles/` for environment variants, `prompts/` for agent-specific prompt layers, `templates/` for reusable blueprints, `scripts/` for utilities, `tests/` for validation, `examples/` for reference content, `assets/` for supporting files, and `docs/` for human-readable architecture and workflow documentation.

## Consequences

- Framework rules remain centralized.
- Documentation stays explicit and navigable.
- Agent integrations stay separated from project code.
- Future extension is easier without collapsing into one folder.

## Alternatives Considered

- Flat repository root with mixed content
- Prompt-only repository
- Script-first repository
