# ADR-0002: Repository Taxonomy

## Status

Proposed

## Context

Sprint 1 included two independent architecture reviews, one by Kiro and one by Hermes. Both reviews reached the same structural conclusion: current repository taxonomy mixes policy and standard concerns, leaves `core/standards/` empty, places `MASTER_PROMPT` outside policy scope, places `USER_PROFILE` outside `profiles/`, describes roadmap items too narratively, and documents an `Engine` layer that is not yet represented in repository structure.

ADR-0001 established the initial repository layout, but Sprint 1 review showed that the layout still needs clearer semantic boundaries before the repository can scale without ambiguity.

## Problem

Current repository naming and placement do not communicate responsibility cleanly.

- Policy content and standard content are blended together.
- `MASTER_PROMPT` is treated like policy, but it is actually an operational prompt artifact.
- `USER_PROFILE` is better modeled as environment- or persona-specific data under `profiles/`.
- `core/standards/` exists in concept but has no clear content model yet.
- `ROADMAP.md` reads like descriptive status text instead of a taxonomy-backed plan.
- Documentation references an `Engine` layer, but the repository does not yet expose that layer in its structure.

This creates drift between docs and repository structure, and it increases the chance that future additions will be placed by convention instead of by clear rule.

## Decision

Adopt a stricter repository taxonomy with explicit semantic separation:

- `core/policies/` for governing rules and decision constraints.
- `core/standards/` for concrete standards, conventions, and normative formats.
- `prompts/` for prompt artifacts such as `MASTER_PROMPT`.
- `profiles/` for user, environment, or persona profiles such as `USER_PROFILE`.
- `docs/engine/` or equivalent documentation grouping for the `Engine` layer until repository implementation catches up.
- `ROADMAP.md` should remain a planning artifact, but its wording should map to repository taxonomy rather than free-form narrative.

This ADR does not move files. It defines the classification rules that future repository work must follow.

## Consequences

- Clearer separation between policy, standard, prompt, and profile concerns.
- Less ambiguity when adding new files or deciding where existing concepts belong.
- Easier review of architecture changes because terminology matches repository structure.
- `core/standards/` gains a defined purpose rather than remaining an empty placeholder.
- Documentation and repository structure become easier to keep aligned.
- Some existing references may need later cleanup to match the taxonomy.

## Alternatives Considered

- Keep current layout and rely on naming convention alone.
- Fold standards into policy and avoid separate taxonomy.
- Move `MASTER_PROMPT` into `core/` with policy content.
- Leave `USER_PROFILE` at repository root for simplicity.
- Treat `Engine` as documentation-only until implementation exists.
